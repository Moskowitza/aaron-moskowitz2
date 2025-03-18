<svelte:head>
  <title>Moving to M4</title>
</svelte:head>

<section class="container">
  <h1 class="name">Intel to M4</h1>

  <p class="body large-letter">
    I finally made the jump from using an Intel MacBook Pro to an M4 MacBook Pro. I let the transfer
    tool run over night and was pretty happy seeing everything set up in the morining. VS Code is
    set up, my github keys were copied, and things generally looked the same. iCloud was still
    showing the sync icon even though it seems like things are all set. Days later icloud still
    seems to be syncing. I've finally got around to working on this site and started tripping over
    problem after problem.
  </p>
  <p class="body">
    I've been uninstalling and reinstalling a lot of the applications I use. iTerm was showing a
    litteny of complants. That set of issues seemed to be with the oh-my-ZSH plugins and apps I've
    installed with homebrew. By the time I was reinstalling node for the 2nd time I realized i made
    a terrible deciion using the transfer tool at all.
  </p>
  <p class="body">
    Here are some helpful things to check on while removing everything and starting over.
  </p>
  <ul class="body">
    <li>
      Move VS Code to the trash <a href="https://code.visualstudio.com/docs/setup/uninstall"
        >guide</a
      >
    </li>
    <li>Delete $HOME/Library/Application Support/Code and ~/.vscode.</li>
    <li>reinstall VS Code</li>
    <li>reinstall extensions, if there are still installed extensions, star over</li>
  </ul>

  <p class="body">
    I used Brew to install node, asdf,Go, and a bunch of other items. So I figured I would use Brew
    to brew uninstall these packages. Maybe that worked the first go around but I <a
      href="https://docs.brew.sh/FAQ#how-do-i-uninstall-homebrew"
    >
      uninstalled brew</a
    > and reinstalled it. I ran brew uninstall. I also had to remove plugins from my ~/.zshrc I wanted
    to make sure I was running the correct version of node and found this command helpful `node -p "process.arch"`
  </p>
</section>
