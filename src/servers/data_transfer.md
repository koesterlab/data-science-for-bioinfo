# data transfer onto and from linux servers

## FTP with Filezilla

Filezilla gives you a nice graphical user interface for data transfer, if you have an (S)FTP server interface available.
You connect very easily and have a sane way of transferring data with a tree- and folder-view for both source and destination.
And you can monitor the transfer while it is happening, and flexibly configure an overwrite policy if necessary.
In general, any transfer should usually work with the following steps:

1. Install Filezilla: [https://filezilla-project.org/](https://filezilla-project.org/)
2. Connect to the server via `Quickconnect` in the top bar:
  * `Host`: `(s)ftp://<server_address>`
  * `Username`: `<user_name>` (optional, only if authentication is necessary)
  * `Password`: `<password>` (optional, only if authentication is necessary)
  * `Port`: `<port>` (optional, only if a non-standard port is specified in the server's documentation)
3. On both panels, navigate to the folders (locally where the data is, remotely where it should go).
4. Highlight files you want to transfer.
5. Right-click and select Upload.

## rsync (via ssh)

If you have a Unix shell / linux command line available on the machine that you are trying to transfer data to or from, this is usually the easiest and most robust way of transferring data.
You can quickly transfer full folders recursively, with rsync optimizing the transfer speed and keeping things like modification timestamps intact.

A command that will take the folder at `/abs/src/path/folder` and transfer it to `/abs/dest/path/folder` is (assuming, you are on the `source` machine):

```
rsync -avP /abs/src/path/folder <user>@<dest_server_address>:/abs/dest/path/folder
```

The command line options used here are:

* `-a`: short for `--archive` mode, which sets `-rlptgoD` (no `-H`,`-A`,`-X`):
  * `-r`: `--recursive`ly copy sub-directories
  * `-l`: copy sym`--links` as symlinks
  * `-p`: short for `--perms`, preserve the permissions
  * `-t`: preserve the modification `--times`
  * `-g`: preserve the `--group`
  * `-o`: preserve the `--owner` (if you are the super-user)
  * `-D`: summary flag for:
    * `--devices`: preserve device files (super-user only)
    * `--specials`: preserve special files
* `-v`: produces more `--verbose` output, useful for debugging when errors occur
* `-P`: summary flag for:
  * `--partial`: keep partially transferred files
  * `--progress`: show progress during transfer

Also, if you want to **rename the folder** during the transfer, you just [add a trailing `/` to the source path](https://unix.stackexchange.com/a/178095):

```
rsync -avP /abs/src/path/folder/ <user>@<dest_server_address>:/abs/dest/path/new_folder
```

Then everything within the source folder gets copied to the destination folder.

The same commands as given above, can also be run to **download things from a server** to a local machine.
In that case, you simply make the server address and path your source, and you local path your destination:

```
rsync -avP <user>@<server_address>:/abs/remote/path/folder /abs/local/path/folder
```

And either of the `local` paths can also be a relative path.
So if you are for example in a folder `/home/user42/` that holds a subfolder `folder/`, you can do:

```
rsync -avP folder <user>@<dest_server_address>:/abs/dest/path/folder
```