# Snakemake

[Snakemake](https://snakemake.readthedocs.io) is a workflow management system to create reproducible and scalable data analyses in a human readable, Python based language. 
You define individual analysis steps as `rules` with a defined `input` and `output`, where dependencies are defined implicitly when the `input` of one rule matches the `output` of another rule.

If you want to get to know its core features, there is a [great snakemake tutorial](https://snakemake.readthedocs.io/en/latest/tutorial/tutorial.html) that is easy to set up and has excersises to work through at your own pace.
And once you have a general understanding of how snakemake works, you could for example try to use one of the standardized [snakemake workflows](#snakemake-workflows-reusable-analysis-workflows).

## Snakemake workflows: reusable analysis workflows

The [snakemake module system](https://snakemake.readthedocs.io/en/latest/snakefiles/modularization.html#modules) allows for flexibly combining different existing workflows for more complex analyses.
It is also used for the deployment of standardized workflows that you can find in the [snakemake workflow catalog](https://snakemake.github.io/snakemake-workflow-catalog/#standardized).
Just click on the `Usage` button of any of the listed standardized workflows to get a walkthrough of how to set up this workflow for your own data analysis (for example the [`dna-seq-varlociraptor` workflow `Usage`](https://snakemake.github.io/snakemake-workflow-catalog/?usage=snakemake-workflows/dna-seq-varlociraptor)).

## Snakemake wrappers: reusable snakemake rules

[Snakemake wrappers](https://snakemake-wrappers.readthedocs.io) are reusable snakemake rules.
They wrap one command of a command line tool to provide a specific output from a provided input file.
You can simply copy-paste such a wrapper into your own workflow use it.
Just check out the compendium of [wrappers](https://snakemake-wrappers.readthedocs.io/en/stable/wrappers.html) and [meta-wrappers](https://snakemake-wrappers.readthedocs.io/en/stable/meta-wrappers.html) (copy-pastable collections of wrappers to perform analysis multiple steps).
And if the tool or command you are looking for is not yet on there, consider [contributing a new snakemake wrapper](https://snakemake-wrappers.readthedocs.io/en/stable/contributing.html), once you have got the tool working in your own workflow.

## Snakemake debugging tricks

### Saving time on DAG building and resolution

To quickly debug a particular rule, specify the output of that rule as the desired output of your `snakemake` run. To avoid clashes with command line argument specifications, it is best to provide the desired output file as the 1st argument right after `snakemake`, e.g.:

```python
snakemake path/to/wanted_output.txt --jobs 5 --use-conda
```

### language-specific debugging

#### R

##### logging

Standard code we use for redirecting any `stderr` output to the `log:` file specified in the rule calling the `R` script:

```r
log <- file(snakemake@log[[1]], open="wt")
sink(log)
sink(log, type="message")
```

##### interactive debugging

You can save the entire current state of a workspace in `R`, so you can insert this right before some code triggers an error:

```r
save.image(file = "my_dump.RData")
```

In an interactive R session, you can then load this workspace and interactively explore / debug what’s going on:

```r
load("my_dump.RData")
```

#### python

##### logging

Standard code we use for redirecting any `stderr` output to the `log:` file specified in the rule calling the python script:

```python
import sys
sys.stderr = open(snakemake.log[0], "w")
```

##### interactive debugging

Inserting the following into a python script executed in a snakemake rule will throw you into an interactive python debugging shell where you have access to the current state, including `locals()` and `globals()` variables:

```python
import pdb; pdb.set_trace()
```