### Exercise: using sshfs

1. make a temporary directory somewhere (easiest using `mktemp -d`), we'll call it `dir1`
2. create a file with some contents and save it in `dir1`
3. create another temporary directory, `dir2`
4. use `sshfs` to mount `dir1` onto `dir2` using:

```bash
sshfs localhost:/path/to/dir1 /path/to/dir2
```

5. go to `dir2`. The file you created in step 2. above should be present there!
6. finally, unmount `dir1` from `dir2` using:

```bash
umount /path/to/dir2
```

[Previous](sshfs.md)

[Next](tmux.md)
