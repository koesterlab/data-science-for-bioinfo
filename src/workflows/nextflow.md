# Nextflow

[Nextflow](https://www.nextflow.io/) is a scalable and reproducible workflow management system written in Groovy and Java using a custom domain-specific language (DSL).
It is centered around three main concepts: [Processes](https://www.nextflow.io/docs/latest/process.html), [Channels](https://www.nextflow.io/docs/latest/channel.html), and [Workflows](https://www.nextflow.io/docs/latest/workflow.html). Nextflow processes receive an input, perform computations, and produce an output. Processes can depend on one another, thus they are connected through channels.
When multiple processes are linked together by channels, they form a Nextflow workflow.

If you want to learn more about Nextflow, you can checkout the [Nextflow Training](https://training.nextflow.io/).

## nf-core: reusable Nextflow workflows

The bioinformatics community developed various computational Nextflow pipelines.
These curated workflows are stored in a central location called nextflow core, also abbreviated as [nf-core](https://nf-co.re/).

nf-core can be installed for example via the package manager [conda](https://nf-co.re/docs/nf-core-tools/installation).

## debugging Nextflow workflows

If you encounter any errors during the execution of your Nextflow pipeline, Nextflow has some nice [training material on troubleshooting](https://training.nextflow.io/basic_training/debugging/).

Also, you can try setting some environment variables before running nextflow, either interactively or by defining them in your `~/.bashrc`, and by increasing the number specified, you can increase the amount of logging information that is provided:

```bash
export NXF_DEBUG=1
export APPTAINERENV_NXF_DEBUG=1
```

You can find more information in the [documentation of `Nextflow` environment variables](https://www.nextflow.io/docs/latest/reference/env-vars.html#nextflow-settings).
