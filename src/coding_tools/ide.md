# integrated development environments (IDEs)

If all you want to do is done in `R`, your best choice of IDE is probably [`Rstudio`](https://posit.co/products/open-source/rstudio/).
For all other purposes, you will have to look around and try what works for you.

## Microsoft Visual Studio Code

[VS Code](https://code.visualstudio.com/) offers a lot of plugins for all common languages, plus lots of useful plugins for other stuff (and all for free).
It has [extensive documentation](https://code.visualstudio.com/docs), but the best way to get started is probably to simply [download VS code](https://code.visualstudio.com/download) and jump right in.
Several people in our group currently use it, with the possibility to [work on a remote project on a server via ssh](https://code.visualstudio.com/docs/remote/ssh) a very useful and heavily used feature.

### recommended VS Code plugins

VS Code has a very lively [Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-marketplace) that provides lots of useful plugins.
Here are some that have proven very useful to us:

* The [`remote ssh`](https://code.visualstudio.com/docs/remote/ssh) extension enables you to log onto a server via an [`ssh` connection](../servers/ssh.md). You can then open a project folder and browse and edit files, while you can also open a Terminal / shell to run commands.
* The [`snakemake`](https://github.com/snakemake/snakemake-lang-vscode-plugin#snakemake-language-support) extension gives you syntax highlighting for `Snakefile`s.
* The [`Rainbow CSV`](https://github.com/mechatroner/vscode_rainbow_csv#rainbow-csv) extension gives you systematic per-column colors in comma-separated and tab-separated value files.
* The [`Edit CSV`](https://github.com/janisdd/vscode-edit-csv) extension allows you to edit `.csv` and `.tsv` files in a tabular view, so that you can create and delete columns and rows, and copy-paste things.

In addition, VS Code will often offer you to install plugins for filetypes you open, or for languages that you use.
Explore.

## Jet Brains

Jet Brains develops a [suite of IDEs for different languages](https://www.jetbrains.com/products/#type=ide-vs) (just use the language filter on the right) and offers a [free version for academic purposes](https://www.jetbrains.com/community/education/#students).
