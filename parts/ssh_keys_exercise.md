### Exercise: key files

1. generate an SSH key file using `ssh-keygen`
2. copy the key to some remote using `ssh-copy-id -i [FILE] [USERNAME]@[HOSTNAME]`
3. try to connect to a remote using `ssh -i [FILE] [USERNAME]@[HOSTNAME]`. There shouldn't be a password prompt from the remote this time.
4. add the key to your SSH agent
5. try connecting to the remote using `ssh [USERNAME]@[HOSTNAME]`. With any luck, you won't see any password prompts this time either!

[Previous](ssh_keys.md)

[Next](ssh_config.md)
