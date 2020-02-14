Timothy Gan, Randal Donaldson
================

## GitHub Documents

This is an R Markdown format used for publishing markdown documents to
GitHub. When you click the **Knit** button all R code chunks are run and
a markdown file (.md) suitable for publishing to GitHub is generated.

## Including Code

You can include R code in the document as
    follows:

``` r
library(tidyverse)
```

    ## ── Attaching packages ───────────────────────────────────────────────── tidyverse 1.3.0 ──

    ## ✓ ggplot2 3.2.1     ✓ purrr   0.3.3
    ## ✓ tibble  2.1.3     ✓ dplyr   0.8.3
    ## ✓ tidyr   1.0.2     ✓ stringr 1.4.0
    ## ✓ readr   1.3.1     ✓ forcats 0.4.0

    ## ── Conflicts ──────────────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
ABIA = read.csv("data/ABIA.csv")
security_summ = ABIA %>%
  group_by(DayOfWeek)  %>%  # group the data points by model name
  summarize(DepartureDelay.mean = mean(DepDelay, na.rm=TRUE))  # calculate a mean for each model

ggplot(security_summ, aes(x=DayOfWeek, y=DepartureDelay.mean)) + 
  geom_bar(stat='identity')
```

![](Exercise1_files/figure-gfm/ABIA-1.png)<!-- --> \`\`\`

## Including Plots

You can also embed plots, for example:

![](Exercise1_files/figure-gfm/pressure-1.png)<!-- -->

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.
