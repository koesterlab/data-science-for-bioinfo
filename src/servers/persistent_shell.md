# persistent screen sessions

A number of tools allow you to set up persistent `bash` sessions on a server (or another computer) that can continue to run when you log off / disconnect from them and that can have multiple windows (shell sessions / terminals) open at once.
Thus, commands (and terminal session histories) will be kept alive even when logged out, and you can easily re-attach to a session that is still running. 
Here we introduce some that are commonly used.


## screen

[`screen`](https://www.gnu.org/software/screen/manual/screen.html) is one such tool for persisten shell sessions that you can detach from, and reattach to later, keeping it running in the background.

### Essential instructions

The bare essentials are described in this guide:
* [**How To Use Linux Screen**](https://linuxize.com/post/how-to-use-linux-screen/)

And the most important command line arguments and keystrokes can be found in this reference:
* [**`screen` Quick Reference**](https://aperiodic.net/screen/quick_reference)
 
And if you are looking for a more detailed intro, check out the [**Getting Started** section of `screen`'s online documentation](https://www.gnu.org/software/screen/manual/screen.html#Getting-Started).

## TMUX

[Tmux](https://github.com/tmux/tmux/wiki) stands for 'terminal multiplexer'.
It is also meant for running commands and workflows in persistent terminal sessions that you can log out of.

### Essential instructions

1. Create a new session with a name:

```
tmux new -s test
```
2. Detach the session that is created with `Ctrl+B` and release `Ctrl` and `B`, then quickly `D`, so it's basically `Ctrl+B` and `D`. The release of `Ctrl` and `B` is important to not _kill_ the session instead of _detaching_ (yes, it happens). The message should indicate: 

```
[detached (from session test)]
```
3. List the session that is created:

```
tmux ls
```
4. Then, to be able to reach the newly created session back again:

```
tmux attach -t test
```
### Other shortcuts that can be useful

```
CTRL - B - [ //scroll mode
q //exit scroll mode
```