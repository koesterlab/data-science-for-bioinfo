# color palettes

Color palettes are a central tool in data visualization.
Thus, it's important to learn [which color scale to use when](https://blog.datawrapper.de/which-color-scale-to-use-in-data-vis/).
And for any visualization using color, please make sure to use colorblind safe palettes:

## color blind friendly palettes

If you just want a color blind color scale, here are some great resources:

* [Okabe Ito colorblind safe palette](https://jfly.uni-koeln.de/color/#pallet):
  In addition to the linked palette, the website also gives good recommendations for colorblind proofing figures.
* [Color Brewer 2](https://colorbrewer2.org):
  With this interactive color palette chooser, you can select sequential, diverging and qualitative colo scales.
  It has a checkbox to restrict results to colorblind safe palettes.
  In R, these color palettes are directly available in the [`ggplot2` package via the `scale_colour_brewer()`](https://ggplot2.tidyverse.org/reference/scale_brewer.html), or generally in R via the [`RColorBrewer` package](https://cran.r-project.org/web/packages/RColorBrewer/index.html).

If you're looking for a thorough introduction to the topic, datawrapper has you covered with a three-part blog series:

1. [How your colorblind and colorweak readers see your colors](https://blog.datawrapper.de/colorblindness-part1/)
2. [What to consider when visualizing data for colorblind readers](https://blog.datawrapper.de/colorblindness-part2/)
3. [What’s it like to be colorblind](https://blog.datawrapper.de/colorblindness-part3/)
