# ssh

[`ssh`](https://www.ssh.com/academy/ssh) allows for secure remote access to servers or other computers over insecure networks (including the internet).

## getting started with ssh

While there is [extensive documentation on `ssh` commands](https://www.ssh.com/academy/ssh/command) and related commands such as [`scp` (for copying files using the ssh protocol)](https://www.ssh.com/academy/ssh/scp), the following Wiki page will probably get you started pretty quickly:

* [WikiHow page **How to Use SSH**](https://www.wikihow.com/Use-SSH)

## ssh keys

ssh key files are a great way to set up safe ssh connections, and if properly set up with your operating system keychain, you can save on a lot of password typing.
There's a [great guide for generating and setting up ssh keys](https://www.ssh.com/academy/ssh/copy-id) that you can quickly work through step by step.
No need to remember any of this by heart, just look it up when you need it.

## `known_hosts`

The `.ssh/` folder in your user home directory (so `~/.ssh/` on a Linux system), contains the `known_hosts` file.
This file keeps track of all of the remote machines you have already connected to, by recording their key fingerprint when you first connect to them.
Thus, the first time you connect to a new server, you will be asked for confirmation of the key fingerprint---either directly on the command line, if that is where you ran the ssh command, or via some interactive menu if you are connecting via some interface (for example with VSCode or Positron).
Usually, you should check this against the expected fingerprint, which you might be able to obtain from your system administrators, from some internal documentation or from a public listing of them, or ensure that accepting this fingerprint is OK.

And whenever you reconnect to a server, `ssh` checks whether this fingerprint is still the same.
If it changes, this indicates a change of the server behind the address you are connecting to and the connection is stopped.
On the command line, the offending key (and potential fix) is immediately listed, in interfaces this often fails silently and you have to sort this out manually (see below).
You have to then establish, whether the fingerprint change is expected and the new fingerprint is correct, because this might also indicate a security breach of the server.

If you are sure the fingerprint change is OK, you have to remove the existing entry and confirm the new one upon your next connection attempt.
The removal can either be done via the command that `ssh` suggests on the command line.
Or you can open the file `~/.ssh/known_hosts` in an editor, look for the line(s) for the server you are trying to connect to and delete them manually.
Don't forget to save the file, before you try connecting again.
