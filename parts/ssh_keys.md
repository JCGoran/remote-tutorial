### Passwords vs. key files

Usually when connecting, the remote asks for a password every time;
it's a bit tedious to do this every time though, and there's a much nicer way of connecting to remotes using **key files**[^pki].

[^pki]: using so-called public-key cryptography


### Generating key files

To generate a key file, run:

```bash
ssh-keygen -b [SIZE] -f [FILENAME]
```

Example:

```bash
ssh-keygen -b 4096 -f $HOME/.ssh/id_rsa
```

followed by a prompt to enter a passphrase for the file, which can be left blank if you want.

This creates two files: a _public_ key (with a `.pub` extension), which can be shared freely, and a _private_ key, which _must not be shared_


### Copying key files

How do we let the remote know we want to use a key to login?
2 ways to handle this:
* We specify the key file each time when connecting:

```bash
ssh -i [FILENAME] [USERNAME]@[HOSTNAME]
```

* we copy the key to the remote:

```bash
ssh-copy-id -i [FILENAME] [USERNAME]@[HOSTNAME]
```

After the password prompt, the remote is (once and for all) aware that the key exists.


### Troubleshooting

Does the remote still prompt for a password?
2 likely reasons:
1. key was not added to SSH agent; run `ssh-add [FILENAME]`
2.  SSH agent itself is not running; run `ssh-agent`, then go to 1.


### Deleting keys

In principle, deleting a key can be done by just deleting the generated private key on your machine.
Alternatively, you can remove the key from the remote as well by deleting the corresponding entry at `~/.ssh/authorized_keys`


[Previous](ssh_exercise.md)

[Next](scp_exercise.md)
