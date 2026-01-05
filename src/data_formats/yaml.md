# YAML syntax

> YAML is a human friendly language for the communication of data between people and computers.
> The language is rich enough to represent almost any conceivable data structure or object inside a running computer program, as a readable plain text file. This type of language is often called a “serialization language” and YAML is definitely one of those.
> But unlike most serialization languages, the YAML format tries hard to make simple things really simple.

This is how the [YAML data project](https://yaml.com/) puts it, and it's spot on.
Thus, for anything where we need configuration files that should be readable by both humans and machines, we use the YAML language.

## learning YAML

* [15 minute YAML tutorial for the most important aspects](https://www.yaml.info/learn/index.html)
* [best practices](https://www.yaml.info/learn/bestpractices.html)

## debugging YAML

To get line-specific infos on `yaml` formatting issues, you can use [`prettier`](https://prettier.io/docs/), an opinionated code formatter that supports `yaml` among a bunch of other formats.
It is available via the `conda-forge` channel, so you can install it into its own `prettier` conda environment with:
```
conda create --channel conda-forge -n prettier prettier
conda activate prettier
```

You can then run it on a yaml file using the `--check` flag to pinpoint formatting issues.
For example, on a file `config.yaml` in the `config/` subdirectory, this would be:
```
prettier --check config/config.yaml
```

## YAML specification

[ALL the gory details in the official specification](https://yaml.org/spec/1.2/).
