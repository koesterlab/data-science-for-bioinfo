# regular expressions

[![Wait, forgot to escape a space. Wheeeeee\[taptaptap\]eeeeee.](https://imgs.xkcd.com/comics/regular_expressions.png)](https://xkcd.com/208)

As the above [xkcd](https://xkcd.com) comic suggests, [regular expressions](https://en.wikipedia.org/wiki/Regular_expression) are a really powerful tool to systematically search (and replace) strings in very large text files.
If you have ever used search-and-replace in a word processor or a spreadsheet software, you have probably seen cases where just searching for a particular word doesn't do the trick.
This is where regular expressions come in.

To get started, it makes sense to familiarize yourself with the general principal of regexes.
For example, check out the [regular-expressions.info Quick Start](https://www.regular-expressions.info/quickstart.html).
As this introduction also mentions, you will then have to venture on to learn how exactly regular expressions work in the language or tool you want to use.

## regular expression flavours

Here comes a tables with resources on the exact regular expression syntax in different tools and languages.
These are often referred to as regular expression flavours.

| language / tool                    | cheat sheet       | reference      | further resources    |
| ---                                | ---               | ---            | ---                  |
| [linux tools (awk, sed, grep, etc.)](../command_line/linux_tools.md) |    | [Basic and Extended regexes](https://www.grymoire.com/Unix/Regular.html) |   |
| [python](../languages/python.md)   |                   | [`re` module](https://docs.python.org/3/library/re.html) / [regex HOWTO](https://docs.python.org/3/howto/regex.html#regex-howto) | [browser-based regex testing](https://pythex.org/) |
| [R](../languages/r.md)             | [`stringr` package](https://stringr.tidyverse.org/index.html#cheatsheet) | [regular expression vignette](https://stringr.tidyverse.org/articles/regular-expressions.html) |