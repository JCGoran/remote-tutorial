### Browsing remote files locally

Sometimes you want to go through files on the remote without having to copy them back and forth all of the time.
A lightweight solution to this is given by SSHFS (on Debian-based Linux, available under the package `sshfs`).


### Using SSHFS

The basics syntax of the command is is:

```bash
sshfs [OPTIONS] [USERNAME]@[HOSTNAME]:[ORIGIN] [DESTINATION]
```

where `[ORIGIN]` is an existing path (directory) on the remote, and `[DESTINATION]` is an empty directory on your local machine.
Now you can browse (and modify of course) files on the remote like they are on your own machine!

When you're done, you can "disconnect the directory" via:

```bash
umount [ORIGIN]
```

[Previous](scp_exercise.md)

[Next](tmux.md)
