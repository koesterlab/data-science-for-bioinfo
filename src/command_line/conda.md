# conda (software installation)

> Conda is an open-source package management system and environment management system that runs on Windows, macOS, and Linux. Conda quickly installs, runs, and updates packages and their dependencies.

This is how the [`conda` documentation](https://docs.conda.io/projects/conda/en/latest/index.html) puts it.
One more major selling-point: you don't need administrator rights to install conda itself or to install packages with it.
And for our (bioinformatic) purposes, there are two more very useful aspects:

1. There is [`bioconda`](../bioinformatics/bioconda.md), a [`conda` channel](https://docs.conda.io/projects/conda/en/latest/user-guide/concepts/channels.html) with pretty much any tool in bioinformatics pre-packaged for you.
2. `conda` seemlessly [integrates with `snakemake`](https://snakemake.readthedocs.io/en/latest/snakefiles/deployment.html#integrated-package-management) for automatic software installation in automated analysis workflows.

## installing conda

We recommend using the [miniforge installation](https://github.com/conda-forge/miniforge#install) and recommend a `conda` version `>= 24.7.1`.
The latter is the [minimum conda version that `snakemake` requires at the time of writing](https://github.com/snakemake/snakemake/releases/tag/v8.20.6) (since [`conda >= 23.10.0`, it uses the fast dependency solver previously only included in `mamba`](https://docs.conda.io/projects/conda/en/latest/release-notes.html#id58)).

## creating and using environments

`conda` makes it easy to [create and manage new (named) software environments](https://docs.conda.io/projects/conda/en/latest/user-guide/getting-started.html#managing-environments).
We recommend to create a new (and minimal) software environment whenever possible (for example, in a snakemake workflow, each rule will have its own software environment).
You will then only activate that software environment whenever you need the software installed into it.
By keeping environments minimal, you avoid clashes in the dependencies that software might have (for example, if software X needs python version 3, while software Y still requires python version 2, these cannot be installed into the same environment---but X and Y will happily install in separate environments, which will pull in the required python version).

But, long story short, here's the command to create an environment:

```bash
conda create -n snakemake_env snakemake snakedeploy snakefmt
```

You can then activate that environment with:

```bash
conda activate snakemake_env
```

And you will be able to call the installed tools, for example `snakemake`:

```bash
snakemake --version
snakemake --help
```

If you are done with your current session of using the software, the following gets you back to your original environment (the one you were in before activating `snakemake_env`):

```bash
conda deactivate
```

If you no longer need the entire environment (and the software contained in it) and want to delete it, you can:
```bash
conda env remove -n snakemake_env
```

And then, there are [many other things you can do with environments](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)---just look up the details whenever you need them.

## installing specific versions of software

Sometimes, you want to install a specific version of a software, for example because something was proven to work with that version in the past.
You can achieve this with:

```bash
conda create -n snakemake_env_7_19_1 snakemake=7.19.1
```

And in case you ever need to dive into the details, there is of course [documentation on how `conda` handles version number specifications](https://docs.conda.io/projects/conda/en/latest/user-guide/concepts/pkg-specs.html#package-match-specifications).
