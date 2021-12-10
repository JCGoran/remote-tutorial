## Part 2: Persistent command-line environments with tmux


### Running commands persistently

Sometimes you may want to run a command "in the background" and disconnect from the remote.
The usual solution is:
```bash
nohup command
```
Downsides:

* difficult to stop/interrupt it (need to hunt down process ID)
* no way to re-attach to the process and do something interactive
* need to dig through a file to see any potential output

**Question**: can we run re-attachable commands after disconnecting?


### Typical workflow with remotes

The typical workflow with a remote goes something along these lines:
* connect to it via `ssh`
* setup your environment (change to the right dir, open the right files, run the right commands, etc.)
* do some actual work

**Question**: since step 2 can be tedious, can we eliminate it?

### Persistent environments with tmux

solution to our problems: tmux[^tmux-name]

* allows us to have a persistent session (at least until a machine reboots), which lets us define our environment _once_, and then re-attach to it whenever

[^tmux-name]: stands for **t**erminal **mu**ltiple**x**er


### Some tmux basics

To make things easier, create a file `~/.tmux.conf` (if it doesn't exist), and insert this line:

```plaintext
set -g mouse on
```

This makes it possible to use your mouse to perform many of the operations below without using the keyboard too much.
If your tmux version is < 1.8, (can be verified with `tmux -V`), insert this instead:

```plaintext
set -g mouse-select-window on
set -g mouse-select-pane on
set -g mouse-resize-pane on
```

* make a new session and connect (attach) to it: `tmux new -s [NAME]`, where `[NAME]` is the name you want to call the session (if not specified, will default to a number). By default, tmux starts a new session in the current working directory (whatever `pwd` is)
* disconnect from the session: once inside of a session, press <kbd>Ctrl</kbd>+<kbd>B</kbd>, followed by <kbd>D</kbd>. Alternatively, write `tmux detach` while attached to a session
* list running sessions: run `tmux ls`. If there aren't any sessions running, tmux will report `No such file or directory` or `No server running on [PATH]`
* re-attach to an existing session: `tmux a -t [NAME]`
* make a new window: once inside of a session, press <kbd>Ctrl</kbd>+<kbd>B</kbd>, followed by <kbd>C</kbd> (as in **C**reate)
* make a new horizontal/vertical _split_: once inside of a session, press <kbd>Ctrl</kbd>+<kbd>B</kbd>, followed by <kbd>"</kbd> (for a horizontal split) / <kbd>%</kbd> (for a vertical split)
* go to the next/previous window: once inside of a session, press <kbd>Ctrl</kbd>+<kbd>B</kbd>, followed by <kbd>N</kbd> (as in **N**ext) / <kbd>P</kbd> (as in **P**revious). If there aren't any windows, tmux will report `No next/previous window`
* switch sessions: once inside of a session,  <kbd>Ctrl</kbd>+<kbd>B</kbd>, followed by <kbd>S</kbd> (as in **S**witch or **S**elect), then select the one with up/down/left/right arrows, and press <kbd>Enter</kbd> to switch to it (bonus: it supports Vim keybindings, so you can use <kbd>H</kbd>/<kbd>J</kbd>/<kbd>K</kbd>/<kbd>L</kbd> instead)

A very useful script is [tmux_completion](https://raw.githubusercontent.com/Bash-it/bash-it/master/completion/available/tmux.completion.bash), which provides <kbd>Tab</kbd> completion in a terminal.

### Workflow with SSH + tmux

Your revised workflow using SSH and tmux should look like the following:

1. SSH to a remote.
2. spawn a new Tmux session, or connect to an existing one.
3. do your work inside the session(s).
4. in case you need to disconnect from the remote for whatever reason (putting your machine to sleep, loss of network connection, etc.), afterwards just go to step 1 - in case you have running sessions, they will remain _exactly_ in the state you left them.

If working on a local machine instead, just skip steps 1 and 4.


[Previous](sshfs_exercise.md)

[Next](tmux_exercise.md)
