## Part 3: Persistent graphical environments with x2go

x2go: like SSH + tmux, but for graphical environments.

Much like SSH, you'll need:

* a machine running an x2go server (the remote)
* a machine running an x2go client (the local machine)

### Basic usage


When you first start x2go, you should be greeted by a prompt like the one below to make a new session:

[session_window.png](session_window.png)

The only mandatory parameters in the above are the _Host_ and the _Login_ fields, which correspond to the hostname and username when using SSH.

If you have an SSH key set up for that remote, then you insert the path to it in the _Use RSA/DSA key..._ field; if you already added that key to the SSH agent, you can just check _Try auto login_ below so you don't have to bother with SSH key passwords.

The only other option that should be changed from the default is the _Session type_, which strongly depends on what's available on the remote; a lightweight desktop environment such as XFCE is usually a safe bet.

Once you fill out the session preferences and click _Ok_, you should see something like this:

[main_window.png](main_window.png)

Once you connect to a remote, you should see something like this:

[x2go_connection.png](x2go_connection.png)

To add a session, click _Session_ → _New session ..._, which will then open up a new window, just like the one when you first started x2go.

When you actually launch a session, the x2go main window should look something like this:

[x2go_while_connected.png](x2go_while_connected.png)

From left to right, the three icons in the lower-right corner of the silver "bubble" denote:

* the 📁 (folder) icon - option to share a folder
* the ⏸️ (pause) icon - suspend the current session
* the ⏻ (shutdown) icon - terminate the current session

Thus, if you want to disconnect from a certain session, but have the option to get back to it, you should click the suspend icon.
Note that the term "suspend" is a bit of a misnomer in this case; the graphical session _will_ actually still be running on the remote, so you should regard the ⏸️ (pause) button as "disconnect from the session, but keep everything running on the remote so I can come back to it later".
On the other hand, the terminate button actually terminates the whole session, in which case, any programs running in the session will close.

If you close the session window by clicking the close button (X or whatever), the session will be suspended instead of terminated.
Depending on how long it takes for the remote to respond to the suspend signal, the session window may take quite some time to actually close, especially on slower networks.

[Previous](tmux_exercise.md)

[Next](x2go_exercise.md)
