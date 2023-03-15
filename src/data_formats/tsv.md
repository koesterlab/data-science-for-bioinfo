# comma-separated or tab-separated value files (CSV/TSV)

## tools

These can also often be handled with [standard linux command line tools](../command_line/linux_tools.md).
However, these usually do not respect header lines and require complicated extra code to deal with those.
The following tools all respect header lines.
However, always be aware of the trade-off between having lots of functionality (or specific functionality like a `join` command) and a cost in processing speed or memory usage that this might incur.

### miller

> [Miller](https://miller.readthedocs.io) is a command-line tool for querying, shaping, and reformatting data files in various formats including CSV, TSV, JSON, and JSON Lines.

Or, to rephrase this: [miller](https://miller.readthedocs.io) is the swiss army knife of CSV/TSV files, you should be able to do almost anything with it.
It uses the linux pipe philosophy, [streaming through input and output](https://miller.readthedocs.io/en/latest/streaming-and-memory/) wherever possible, to also reduce memory usage.
And it employs [multithreading to a certain degree](https://miller.readthedocs.io/en/latest/cpu/), especially for (de-)compression and for multiple commands in its `then`-chains.

### xsv

[xsv](https://github.com/burntsushi/xsv) is not as versatile as miller, but blazingly fast.
It also follows the linux pipe philosophy and streams wherever possible.
If it can do what you are looking for, it is probably the fastest option out there.

### csvkit

[csvkit](https://csvkit.readthedocs.io/) can for example join multiple csv files by a common column at once, using `csvjoin`, whereas other tools will require pipe chaining of multiple calls to their join command for this.
However, it is [a lot slower than `xsv`](https://faraday.ai/blog/how-we-made-our-csv-processing-142x-faster/).