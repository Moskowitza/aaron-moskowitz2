<svelte:head>
  <title>Guitar Tab Maker - Aaron Moskowitz</title>
  <meta name="description" content="Guitar tab maker tool by Aaron Moskowitz" />
</svelte:head>

<script lang="ts">
  type TabPosition = {
    note: string;
    modifier: string;
  };
  
  type TabMeasure = TabPosition[][];
  
  let measures: TabMeasure[] = [];
  let currentNumber = 0;
  let numberBuffer = '';
  let currentModifier = '';
  let hoveredNote: { note: string; x: number; y: number } | null = null;
  
  // Modifier definitions
  const modifiers: Record<string, string> = {
    'b': 'bend',
    'r': 'release', 
    'h': 'hammer-on',
    'p': 'pull-off',
    '/': 'slide-up',
    '\\': 'slide-down',
    '~': 'vibrato',
    '.': 'staccato',
    '(': 'ghostnote'
  };

  // Chromatic note names for each string (standard tuning)
  const stringNotes = ['E', 'A', 'D', 'G', 'B', 'E']; // 6th to 1st string
  
  function getChromaticNote(stringIndex: number, fret: number): string {
    if (fret === -1 || fret === 0) return stringNotes[stringIndex];
    
    const chromaticScale = ['C', 'C#', 'D', 'D#', 'E', 'F', 'F#', 'G', 'G#', 'A', 'A#', 'B'];
    const openNote = stringNotes[stringIndex];
    const openNoteIndex = chromaticScale.indexOf(openNote);
    const noteIndex = (openNoteIndex + fret) % 12;
    return chromaticScale[noteIndex];
  }

  function addMeasure(): void {
    const newMeasure: TabMeasure = [];
    for (let string = 0; string < 6; string++) {
      const line: TabPosition[] = [];
      for (let position = 0; position < 16; position++) {
        line.push({ note: '-', modifier: '' });
      }
      newMeasure.push(line);
    }
    measures = [...measures, newMeasure];
  }

  function handleDashClick(measureIndex: number, stringIndex: number, positionIndex: number): void {
    const position = measures[measureIndex][stringIndex][positionIndex];
    
    if (currentNumber === -1) {
      // Place a dash
      position.note = '-';
    } else {
      // Place a number
      position.note = currentNumber.toString();
    }
    
    // Add modifier if one is selected
    if (currentModifier) {
      position.modifier = currentModifier;
    }
    
    measures = [...measures];
  }

  function handleGlobalKeydown(event: KeyboardEvent): void {
    const key = event.key;
    
    // Handle spacebar to clear modifiers
    if (key === ' ') {
      currentModifier = '';
      return;
    }
    
    // Handle modifier keys
    if (modifiers[key]) {
      currentModifier = key;
      return;
    }
    
    // Handle dash key
    if (key === '-') {
      currentNumber = -1; // Special value to represent dash
      numberBuffer = '';
      return;
    }
    
    // Only handle number keys (0-9)
    if (/^[0-9]$/.test(key)) {
      numberBuffer += key;
      
      // If we have 3 or more digits, reset to 0
      if (numberBuffer.length >= 3) {
        currentNumber = 0;
        numberBuffer = '';
        return;
      }
      
      // Parse the current buffer
      const num = parseInt(numberBuffer);
      
      // Only set if it's a valid number (0-24)
      if (num >= 0 && num <= 24) {
        currentNumber = num;
      }
    }
  }

  function handleGlobalKeyup(event: KeyboardEvent): void {
    const key = event.key;
    
    // Clear buffer on any non-number key (including dash)
    if (!/^[0-9]$/.test(key)) {
      numberBuffer = '';
    }
  }

  // Add global keyboard listeners when component mounts
  import { onMount } from 'svelte';
  
  onMount(() => {
    document.addEventListener('keydown', handleGlobalKeydown);
    document.addEventListener('keyup', handleGlobalKeyup);
    
    return () => {
      document.removeEventListener('keydown', handleGlobalKeydown);
      document.removeEventListener('keyup', handleGlobalKeyup);
    };
  });

  function resetMeasure(measureIndex: number): void {
    const measure = measures[measureIndex];
    for (let string = 0; string < 6; string++) {
      for (let position = 0; position < 16; position++) {
        measure[string][position] = { note: '-', modifier: '' };
      }
    }
    measures = [...measures];
  }
</script>

<div class="container">
  <h1>Guitar Tab Maker</h1>
  
  <div class="controls">
    <button class="add-button" on:click={addMeasure}>Add Measure</button>
    <div class="number-control">
      <span>Current: {currentNumber === -1 ? '-' : currentNumber}</span>
      {#if currentModifier}
        <span class="modifier-display">Modifier: {modifiers[currentModifier]}</span>
      {/if}
      <div class="number-instructions">
        <span>Type numbers (0-24), dash (-), or modifiers (b,r,h,p,/,\,~,.,() on your keyboard</span>
        <span class="modifier-help">Spacebar clears modifiers</span>
      </div>
    </div>
  </div>

  <div class="tab-container">
    {#each measures as measure, measureIndex}
      <div class="measure-wrapper">
        <div class="measure">
                  {#each measure as line, stringIndex}
          <div class="string-line">
            {#each line as position, positionIndex}
              <span 
                class="tab-position" 
                class:clicked={position.note !== '-'}
                on:click={() => handleDashClick(measureIndex, stringIndex, positionIndex)}
                on:mouseenter={(e) => {
                  if (position.note !== '-' && position.note !== '0') {
                    const rect = e.currentTarget.getBoundingClientRect();
                    hoveredNote = {
                      note: getChromaticNote(stringIndex, parseInt(position.note)),
                      x: rect.left + rect.width / 2,
                      y: rect.top - 10
                    };
                  }
                }}
                on:mouseleave={() => {
                  hoveredNote = null;
                }}
              >
                {#if position.modifier === '('}
                  ({position.note})
                {:else if position.modifier}
                  {position.note}{position.modifier}
                {:else}
                  {position.note}
                {/if}
              </span>
            {/each}
          </div>
        {/each}
        </div>
        <button class="reset-button" on:click={() => resetMeasure(measureIndex)}>
          Reset Measure
        </button>
      </div>
    {/each}
  </div>

  {#if measures.length === 0}
    <p class="empty-state">Click "Add Measure" to start creating your guitar tab!</p>
  {/if}

  {#if hoveredNote}
    <div 
      class="note-popover"
      style="left: {hoveredNote.x}px; top: {hoveredNote.y}px;"
    >
      {hoveredNote.note}
    </div>
  {/if}
</div>

<style>
  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
  }

  h1 {
    font-size: 2.5rem;
    color: var(--text-primary);
    margin-bottom: 2rem;
  }

  .controls {
    display: flex;
    gap: 2rem;
    align-items: center;
    margin-bottom: 2rem;
    flex-wrap: wrap;
  }

  .add-button {
    background-color: var(--action-primary);
    color: var(--surface-light);
    border: none;
    padding: 0.75rem 1.5rem;
    border-radius: 8px;
    font-size: 1rem;
    cursor: pointer;
    transition: background-color 0.2s;
    font-weight: 500;
  }

  .add-button:hover {
    background-color: var(--action-hover);
  }

  .number-control {
    display: flex;
    align-items: center;
    gap: 1rem;
    flex-wrap: wrap;
  }

  .number-control button {
    background-color: var(--surface-main);
    color: var(--text-primary);
    border: 1px solid var(--border-light);
    padding: 0.5rem 1rem;
    border-radius: 6px;
    cursor: pointer;
    transition: background-color 0.2s;
  }

  .number-control button:hover {
    background-color: var(--surface-hover);
  }

  .number-instructions {
    font-size: 0.875rem;
    color: var(--text-secondary);
    font-style: italic;
    display: flex;
    flex-direction: column;
    gap: 0.25rem;
  }

  .modifier-display {
    background-color: var(--accent-indigo);
    color: var(--surface-light);
    padding: 0.25rem 0.5rem;
    border-radius: 4px;
    font-size: 0.75rem;
    font-weight: 500;
  }

  .modifier-help {
    font-size: 0.75rem;
    color: var(--text-secondary);
  }

  .tab-container {
    display: flex;
    gap: 1rem;
    overflow-x: auto;
    padding: 1rem 0;
  }

  .measure-wrapper {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    align-items: center;
  }

  .measure {
    border: 2px solid var(--border-light);
    border-radius: 8px;
    padding: 1rem;
    background-color: var(--surface-light);
    min-width: fit-content;
  }

  .reset-button {
    background-color: var(--status-error);
    color: var(--surface-light);
    border: none;
    padding: 0.5rem 1rem;
    border-radius: 6px;
    font-size: 0.875rem;
    cursor: pointer;
    transition: background-color 0.2s;
    font-weight: 500;
  }

  .reset-button:hover {
    background-color: var(--red-600);
  }

  .string-line {
    display: flex;
    gap: 0.25rem;
    margin-bottom: 0.5rem;
    font-family: 'Courier New', monospace;
    font-size: 1.1rem;
  }

  .string-line:last-child {
    margin-bottom: 0;
  }

  .tab-position {
    display: inline-block;
    min-width: 1.5rem;
    height: 1.5rem;
    text-align: center;
    line-height: 1.5rem;
    cursor: pointer;
    border-radius: 4px;
    transition: background-color 0.2s;
    user-select: none;
    padding: 0 0.25rem;
    font-size: 0.875rem;
  }

  .tab-position:hover {
    background-color: var(--surface-hover);
  }

  .tab-position.clicked {
    background-color: var(--action-primary);
    color: var(--surface-light);
    font-weight: bold;
  }

  .empty-state {
    text-align: center;
    color: var(--text-secondary);
    font-style: italic;
    margin-top: 2rem;
  }

  .note-popover {
    position: fixed;
    background-color: var(--surface-main);
    color: var(--text-primary);
    border: 1px solid var(--border-light);
    border-radius: 4px;
    padding: 0.25rem 0.5rem;
    font-size: 0.75rem;
    font-weight: 500;
    z-index: 1000;
    transform: translateX(-50%);
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
    pointer-events: none;
  }
</style>
