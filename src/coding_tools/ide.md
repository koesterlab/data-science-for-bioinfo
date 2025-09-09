# integrated development environments (IDEs)

If all you want to do is done in `R`, your best choice of IDE is probably [`Rstudio`](https://posit.co/products/open-source/rstudio/).
For all other purposes, you will have to look around and try what works for you.

## Microsoft Visual Studio Code

[VS Code](https://code.visualstudio.com/) offers a lot of plugins for all common languages, plus lots of useful plugins for other stuff (and all for free).
It has [extensive documentation](https://code.visualstudio.com/docs), but the best way to get started is probably to simply [download VS code](https://code.visualstudio.com/download) and jump right in.
Several people in our group currently use it, with the possibility to [work on a remote project on a server via ssh](https://code.visualstudio.com/docs/remote/ssh) a very useful and heavily used feature.

### recommended VS Code plugins

VS Code has a very lively [Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-marketplace) that provides lots of useful plugins.
However, as extension can potentially execute malicious code on your machine, please do at least [a basic check whether extensions are safe to install](https://code.visualstudio.com/docs/configure/extensions/extension-runtime-security#_determine-extension-reliability).

Here are some that have proven very useful to us:

* The [`Remote - SSH`](https://code.visualstudio.com/docs/remote/ssh) extension enables you to log onto a server via an [`ssh` connection](../servers/ssh.md). You can then open a project folder and browse and edit files, while you can also open a Terminal / shell to run commands.
* The [`snakemake`](https://github.com/snakemake/snakemake-lang-vscode-plugin#snakemake-language-support) extension gives you syntax highlighting for `Snakefile`s.
* The [`Rainbow CSV`](https://github.com/mechatroner/vscode_rainbow_csv#rainbow-csv) extension gives you systematic per-column colors in comma-separated and tab-separated value files.
* The [`Edit CSV`](https://github.com/janisdd/vscode-edit-csv) extension allows you to edit `.csv` and `.tsv` files in a tabular view, so that you can create and delete columns and rows, and copy-paste things.

In addition, VS Code will often offer you to install plugins for filetypes you open, or for languages that you use.
Explore.

## Positron

[Positron](https://positron.posit.co/) is a free, next-generation, multi-language integrated development environment (IDE) built on Code OSS, the same base as [Microsoft Visual Studio Code](#microsoft-visual-studio-code).
It was designed specifically for data science by [Posit PBC](https://posit.co/) (formerly RStudio) and offers native support for Python and R, making it easy to switch between different versions of these languages.
From a user perspective, it is basically a [mixup between the user interfaces of Rstudio and VS Code](https://positron.posit.co/layout.html), so migration should be relatively easy of you are familiar with either, or both.
The docs even offer migration guides for [Rstudio (Workbench)](https://positron.posit.co/migrate-rstudio.html) and [VS Code](https://positron.posit.co/migrate-vscode.html).

Positron supports Quarto documents and integrates jupyter notebooks, scripts, consoles, and interactive outputs into a unified workspace (rather than an R project), has its own data explorer, AI assistant (Positron assistant), and supports [VSCode extensions](#recommended-vs-code-plugins).
Further, Positron provides essential data analysis workflow functionality via built in extensions, for example [remote ssh sessions](https://positron.posit.co/remote-ssh.html) and [git version control](https://positron.posit.co/git.html).

And if you prefer watching a video to get a quick tour of Positron, see: https://www.youtube.com/watch?v=4Ir_HX4riHw

### recommended Positron plugins

Positron uses [Open VSX](https://open-vsx.org/), an open-source marketplace for VS Code extensions.
As such, you can mostly choose from the same extensions as for VS Code, so have a look at the [VS Code recommendations above](#recommended-vs-code-plugins).
But please note that [Open VSX is only starting to implement security checks for extensions](https://github.com/EclipseFdn/open-vsx.org/issues/5096), so the [checks suggested for credibility of extensions for VS Code are even more import for this marketplace](https://code.visualstudio.com/docs/configure/extensions/extension-runtime-security#_determine-extension-reliability).
Hopefully, it will have much more extensive marketplace protections in the near future.

Note that Positron comes with a number of [vetted and builtin VS Code extensions](https://positron.posit.co/extensions.html#built-in-extensions), which you can list by searching for `@builtin` in the extensions Extensions tab of the left sidebar (blocks symbol).
Among them, is the `Open Remote - SSH` plugin, equivalent to the `Remote - SSH` extension mentioned above, so there's no need to install that yourself.

In addition, there are a couple of useful extension functionalities that Positron does not have built in (yet):

* The [`vscode-pdf`](https://open-vsx.org/extension/tomoki1207/pdf) extension is a PDF viewer, which is also [recommended by the Posit PBC team until there is built in support](https://github.com/posit-dev/positron/issues/4201#issuecomment-2955973660).
* The [`Project Manager`](https://open-vsx.org/extension/alefragnani/project-manager) extension, also [recommended by Posit PBC](https://positron.posit.co/migrate-rstudio-rproj.html#launch-from-the-project-manager-extension), allows you to manage a folder as a unique workspace for a project.


## Jet Brains

Jet Brains develops a [suite of IDEs for different languages](https://www.jetbrains.com/products/#type=ide-vs) (just use the language filter on the right) and offers a [free version for academic purposes](https://www.jetbrains.com/community/education/#students).
