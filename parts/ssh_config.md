### SSH config file

While we don't need a password now, we still need to specify the user and the hostname each time.

Solution: SSH config file at `~/.ssh/config` (may not exist)


### SSH config example

```plaintext
Host [ALIAS]
    HostName [HOSTNAME]
    User [USERNAME]
    IdentityFile [KEY_FILE]
    Port [PORT]
```

* `[ALIAS]`: can be any string, usually short to spare yourself the typing
* `[HOSTNAME]` and `[USERNAME]`: self-explanatory
* `[KEY_FILE]`: the absolute path to the key file (like `/path/to/file`)
* `[PORT]`: the default [networking port](https://en.wikipedia.org/wiki/Port_(computer_networking)) to use for the connection

With the previously generated key file + the config, we can reduce our connection attempt to 6 keystrokes[^keystrokes]:

```bash
ssh x
```

where `x` is an alias for some remote.
We can of course alias this too using a shell alias: `alias x='ssh x'`, but it can make things a bit too ambiguous :)

For more info about the available options, have a look at `man ssh_config`.

[^keystrokes]: the last one being <kbd>Enter</kbd>

[Previous](ssh_keys_exercise.md)

[Next](scp.md)
