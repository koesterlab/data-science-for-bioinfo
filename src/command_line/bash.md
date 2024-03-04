# Unix shell / linux command line / bash

`bash` is the most common Linux shell, a command-line environment where you can enter and thus run commands interactively.
You can find extensive resources about it online, and oftentimes searching for your particular problem online will provide suggestions for solutions.

Here are two **quick-and-easy introductions** that focus on the most important aspects and should be doable in a few hours:
* [Unix Crash Course by Sean Barker (with xkcd comics;)](https://tildesites.bowdoin.edu/~sbarker/unix/), and with some infos on server access on the command-line
* [Unix Crash Course by `csoft.net`](https://www.csoft.net/docs/course.html), with a bit more on file permissions

Here is a very well curated and more **thorough introduction to the command line** with a motivating example running through the course:
* [Software Carpentry introduction to the Unix shell](https://swcarpentry.github.io/shell-novice/)

And some additional material, for those who want to dive in deeper or skip ahead:
* [Software Carpentry introductions to some Unix shell extras](https://carpentries-incubator.github.io/shell-extras/), for example including working remotely (`ssh`), variables, and `awk`

And here are some more detailed resources:

* [Bash Guide for Beginners](https://tldp.org/LDP/Bash-Beginners-Guide/html/index.html): Step-by-step introduction to some of the most important features.
* [Advanced Bash-Scripting Guide](https://tldp.org/LDP/abs/html/): Extensive reference for (almost) all imaginable things in `bash`. For example, you can find a [table of all string operations in `bash`](https://tldp.org/LDP/abs/html/refcards.html#AEN22828).

## bash scripts

You can write full scripts in plain text files, with one command per row and including flow controls (like if-else clauses) in `bash`, so that you can repeat any number of steps easily.
This script can just contain commands, and if it is saved as `path/to/some_script.bash`, you could execute it with:
```bash
bash path/to/some_script.bash
```

Instead, you can also specify that it is a `bash` script within the file, by including the following first line in the file `path/to/another_script.bash` (if you are interested in what this line does, check out [the explanation on stackoverflow](https://stackoverflow.com/a/21613044)):
```bash
#!/usr/bin/env bash
```
If you then make that file executable for your user with `chmod u+x another_script.bash`, you can execute it by simply calling the name:
```bash
path/to/another_script.bash
```
Your shell will know to use the `bash` from your main environment to execute this script.
