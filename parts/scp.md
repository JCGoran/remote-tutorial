### Copying files using scp

We can copy files to and from remotes using the `scp` utility.
To push files from your machine to the remote:

```bash
scp [ORIGIN] [USERNAME]@[HOSTNAME]:[DESTINATION]
```

To pull files from the remote to your machine, invert the order:

```bash
scp [USERNAME]@[HOSTNAME]:[ORIGIN] [DESTINATION]
```

A modern alternative is provided by `rsync`, for which you can use the same syntax.
If you want to do more advanced things (specify alternate SSH ports, etc.), you can explicitly specify you want to use SSH for the transfer with: `rsync -e 'ssh [SSH_OPTIONS]' [ORIGIN] [DESTINATION]`.

[Previous](ssh_config.md)

[Next](scp_exercise.md)
