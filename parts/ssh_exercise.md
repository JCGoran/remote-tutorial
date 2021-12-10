### Exercise: SSH basics

0. open up a terminal
1. connect to some remote using `ssh [USERNAME]@[HOSTNAME]`. If you don't have any at your disposal, run `ssh localhost`.
2. run some non-graphical commands there (like `whoami`, `echo $HOME`, etc.)
3. disconnect from it
4. now try running a command remotely using `ssh [USERNAME]@[HOSTNAME] [COMMAND]`. If it's an interactive command (like `python3`), you will need to specify the `-t` option.
5. if you're running an interactive command, exit from it
6. now try the same as step 4., but with a graphical command (like `firefox`, or `mousepad`, or something else that's installed on the remote). In this case, you will need to pass the `-X` option to your SSH command.


[Previous](ssh.md)

[Next](ssh_keys.md)
