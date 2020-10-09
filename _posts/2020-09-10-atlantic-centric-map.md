---
title: "Plotting Atlantic Centered Map Using R and ggplot2"
# output:
#  html_document:
#    df_print: paged
output:
  md_document:
    variant: gfm
    preserve_yaml: TRUE
knit: (function(inputFile, encoding) {
  rmarkdown::render(inputFile, encoding = encoding, output_dir = "../_posts") })
author: "Ka Ming Fung"
date: '2019-09-10'
excerpt: "Here are two tips for having what I think will be an easier blogging experience in R Markdown and Jekyll."
layout: post
categories:
  - R Markdown
  - Jekyll
tags: R ggplot2 visualization
---

Created by Ka Ming Fung (<kamingfung@mit.edu>)

This is an example to plot a world map with Atlantic centered map using
R and ggplot2.

``` r
library(ggplot2) # for plotting

ggplot() + borders("world2") + coord_fixed(expand = FALSE) + theme_bw()
```

![](/assets/imgs/2020-10-09-atlantic-centric-map/unnamed-chunk-1-1.png)<!-- -->

…and with a bit more informative axes.

``` r
library(scales)  # for formatting axes labels

ggplot() + borders("world2") + coord_fixed(expand = FALSE) + theme_bw() + 
  scale_x_continuous(breaks = c(90, 180, 270), labels = label_number(suffix = "ºE")) + 
  scale_y_continuous(breaks = c(-60, -30, 0, 30, 60), labels = label_number(suffix = "ºN"))
```

![](/assets/img/2020-10-09-atlantic-centric-map/unnamed-chunk-2-1.png)<!-- -->

You can then add other geometry object onto the maps.
