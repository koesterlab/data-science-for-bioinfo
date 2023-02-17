# R

## learning programming with R

If you are new to programming and want to start learning using R, the free online book [Hands-On Programming with R](https://rstudio-education.github.io/hopr/) is a great place to start.
It really starts from scratch, including information on [how to install R and Rstudio](https://rstudio-education.github.io/hopr/starting.html) and getting you acquainted with basic principles of programming through hands-on excercises.

## Stat545: Data wrangling, exploration, and analysis with R

If you are looking for a very detailed and granular introduction to data analysis with R, [STAT545: Data wrangling, exploration, and analysis with R](https://stat545.com) by Jenny Brian *et al.* provides a thorough and accessible course.
You can work through it self-paced.

## interactive learning via `swirl` 
Interactive learning within R command line. From beginner to advanced. User friendly.
[swirl](https://swirlstats.com/)

## R4DS: R for Data Science

If you have programmed before and want to learn how to use R for data analysis, the free online book [R for Data Science](https://r4ds.hadley.nz/) is all you need.
It introduces both concepts and tools in a very accessible way, including example code and coding excercises.
It is based on the [tidyverse](#tidyverse) packages.

## tidyverse

Use the [tidyverse](https://www.tidyverse.org/) for modern, vectorized, and efficient code, with excellent documentation (and cool package badges;).
If you want a thorough introduction, the [R4DS book](#r4ds-r-for-data-science) is there for you.
And if you want to jump right in, here's a table of the most important packages and their online documentation, in the order that you will probably most often use them in a project:

### important packages

| name    | online docs (cheatsheets!)     | purpose |
| ---     | ---                            | ---     |
| readr   | https://readr.tidyverse.org/   | read in (rectangular) data (csv, tsv, xslx, ...) |
| tidyr   | https://tidyr.tidyverse.org/   | get data into tidy format |
| stringr | https://stringr.tidyverse.org/ | string manipulation |
| dplyr   | https://dplyr.tidyverse.org/   | transform data (in tidy format) with sql-like syntax |
| ggplot2 | https://ggplot2.tidyverse.org/ | easy and versatile plotting with the grammar of graphics |

### jump right in

If you do want to jump right in, depending on you previous exposure to the tidyverse, I recommend to at least:

1. Get all the cheatsheets and have those ready on your machine or even printed out.
   Either from the online documentation linked above, or from the Rstudio compilation of all tidyverse cheatsheets.
2. Read through the introductions of the online vignettes above, and the conceptual vignettes that they link to.
   They do a very good job at explaining basic concepts that will make writing analyses with the tidyverse a lot easier and more intuitive.

The most important concepts are probably:

1. Always get your data into a **tidy format** first.
   How tidy data should look and why, is described [in this tidy data vignette](https://tidyr.tidyverse.org/articles/tidy-data.html).
2. When working in the tidyverse, you will always use **pipes**.
   There is a [good introductory chapter on pipes in the R4DS online book](https://r4ds.had.co.nz/pipes.html).
3. There’s also a [vignette on how to work with two tables](https://dplyr.tidyverse.org/articles/two-table.html).
   For example, if you want to filter one table to only include entries also present in a second table.
   Or if you want to use a second table, to add annotation fields to a first table.

### style guide

[https://style.tidyverse.org](https://style.tidyverse.org/)

A detailed and well-written style guide for using R with the tidyverse.
It covers topics like good names, syntax recommendations and best practices for error messages.
Many of the things covered here, can also be applied in other programming languages.

### styler: automatic formatting

[https://styler.r-lib.org](https://styler.r-lib.org/)

Automatic formatting according to tidyverse style guide.
This is also available for [VS Code via the `R` (or `REditorSupport`) extensions](#alternative-ide-r-reditorsupport-extension-for-vs-code).

## Rstudio: an integrated development environment tailor-made for R

Rstudio is an IDE dedicated to R, and probably the most comprehensive IDE for this language and very easy to get going with a productive workflow.
You can get the free desktop version for your operating system on posit's [Rstudio download page](https://posit.co/download/rstudio-desktop/#download).

In Rstudio, you have a console with an interactive R session on the bottom left (like running R on the command line).
Here, you can always conjure up the help information of any function by putting a question mark in front of it (for example `?mutate()`) and hitting enter.
This will open the respective vignette in the bottom right window.
There, you will first find a description of the function and each of its arguments, and further down some quick examples on tibbles (data frames) that are immediately useable in the interactive session.
So just copy and paste them, and start modifying them to your needs.

If you are using Ubuntu as your operating system and want to install R (and R packages) through conda, here's a useful trick:
- Getting Rstudio to use a conda environment with your R installation on Ubuntu: [https://gist.github.com/dlaehnemann/8126c903d560307cb246fa26b52d10de](https://gist.github.com/dlaehnemann/8126c903d560307cb246fa26b52d10de)

### alternative IDE: `R` (`REditorSupport`) extension for VS Code

[https://github.com/REditorSupport/vscode-R](https://github.com/REditorSupport/vscode-R)

Provides full language support for R in VS Code, including code completion, formatting, syntax highlighting, plot and data views, etc. This should make VS Code configurable in the same way that RStudio works.



