# linux tools

Any linux distribution comes with a set of linux tools for the command line.
In bioinformatics (and data science in general), especially the line by line tools for plain text files are very useful.
Thus, we will introduce a number of these tools here and provide links for useful tutorials and documentation for the more complex ones.
However, you can usually get detailed documentation for any of these tools on the command-line.
Simply write `man` followed by the tool's name to get its full manual, for example `man head`.
You can scroll up and down and leave the manual with `q` to drop back to the command-line (controls are the same as the command-line text file viewer [`less`](#less-quick-look-at-text-files)).

## common command-line arguments

Most command-line tools have certain standard command-line arguments, that usually come in a short (one dash `-` and just one letter) and a long version (two dashes `--` and a full word):

* `-h`/`--help`: display a help message
* `--version`: display the version of the tool that you have installed
* `--verbose`: provide more verbose output, oftentimes useful for debugging problems

## `awk`: line by line editing of tabular plain text files

`awk` is a great tool to work on plain-text tabular files (for example tab-separated or comma-separated files, `.tsv` and `.csv` files, respectively).
It provides you with direct accessors to individual columns (for example `$1` for the first column) and with lots of functionality to work with them.

* [awk tutorial for getting started](https://www.grymoire.com/Unix/Awk.html)
* [comprehensive awk reference](https://www.math.utah.edu/docs/info/gawk_toc.html)


## `grep`: line by line plain text file searching

`grep` allows you to search for strings and [regular expressions](../coding_tools/regular_expressions.md) in text files.
It will return any line containing a search string.
For example, `grep "gene" myfile.txt` would return any line containing the string `gene` in `myfile.txt`.


## `head` and `tail`

`head -n 5 myfile.txt` will display the first five lines of the plain text file `myfile.txt`.
`tail -n 5 myfile.txt` will display the last five lines of the plain text file `myfile.txt`.


## `less`: quick look at text files

`less` is a tool for quickly looking at text files on the command line.
Conjure it up with `less myfile.txt`, scroll up and down with the arrow and page up/down keys, search for something like `thisword` with `/thisword` (followed by enter) and quit by hitting `q`.


## `sed`: line by line plain text file editing

`sed` is a great tool to work on plain-text files line by line.
For example, you can easily search and replace patterns using regular expressions.

* [sed tutorial for getting started](https://www.grymoire.com/Unix/sed.html)


## further resources

* [useful bioinformatics one-liners](https://github.com/stephenturner/oneliners): these mostly only use basic linux-tools to achieve common bioinformatics tasks
