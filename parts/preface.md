## Preface

* based on [A brief introduction to remotes](https://jcgoran.github.io/2021/02/23/remote-work.html)
* anything written like <kbd>Ctrl</kbd>+<kbd>X</kbd> denotes actual keys on your keyboard.
A plus sign between them denotes that the keys should be pressed simultaneously.[^apple]
* to add: <kbd>X</kbd> is _not_ the same as <kbd>Shift</kbd>+ the key <kbd>X</kbd> (keyboard usually have uppercase letters on them, but YMMV)
* commands and file content are denoted in a monospaced font, like `echo "Hello world"`
* anything written with square brackets like `[THING]` is something that should be **customized**
* things with a dollar sign, like `${HOME}` denote shell variables. The variable `~` is a synonym for `${HOME}`
* some command-line experience is encouraged
* when in doubt, `man [COMMAND]` and Internet search engines are your friends


### Software used

* (recommended if using a Windows machine): Windows Subsystem for Linux 2 (WSL2)
* an SSH client (any of [these](https://en.wikipedia.org/wiki/Comparison_of_SSH_clients) will do; on Debian, install package `openssh-client`)
* SSHFS: for [MacOS](https://osxfuse.github.io/), or Linux package `fuse-sshfs` (CentOS/Fedora/RedHat) or `sshfs` (Debian/\*ubuntu)
* tmux ([installation from various package managers](https://github.com/tmux/tmux/wiki/Installing))
* (_optional_) x2go ([general installation instructions](https://wiki.x2go.org/doku.php/doc:installation:x2goclient); on Debian, install package `x2go-client`)

[^apple]: On Apple devices, instances of <kbd>Ctrl</kbd> should _probably_ be replaced with <kbd>⌘</kbd>

[Next](ssh.md)
