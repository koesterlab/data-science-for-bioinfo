# TMUX

[Tmux](https://github.com/tmux/tmux/wiki) is a 'terminal multiplexer' for running commands and workflows in persistent terminal sessions that you can log out of.
Thus, commands (and terminal session histories) will be kept alive even when logged out, and you can easily re-attach to a session that is still running. 

## Essential instructions

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
## Other shortcuts that can be useful:

```
CTRL - B - [ //scroll mode
q //exit scroll mode
```
