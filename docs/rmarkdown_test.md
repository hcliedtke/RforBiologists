---
layout: default
title: Rmarkdown test
nav_order: 3
output:
  md_document:
    variant: markdown_github
    preserve_yaml: true
editor_options: 
  chunk_output_type: console
---

## R Markdown

This is an R Markdown document. Markdown is a simple formatting syntax
for authoring HTML, PDF, and MS Word documents. For more details on
using R Markdown see <http://rmarkdown.rstudio.com>.

When you click the **Knit** button a document will be generated that
includes both content as well as the output of any embedded R code
chunks within the document. You can embed an R code chunk like this:

``` r
summary(cars)
```

    ##      speed           dist       
    ##  Min.   : 4.0   Min.   :  2.00  
    ##  1st Qu.:12.0   1st Qu.: 26.00  
    ##  Median :15.0   Median : 36.00  
    ##  Mean   :15.4   Mean   : 42.98  
    ##  3rd Qu.:19.0   3rd Qu.: 56.00  
    ##  Max.   :25.0   Max.   :120.00

## Including Plots

You can also embed plots, for example:

![](/images/pressure-1.png)

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.

## Include ggplot

``` r
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.2     ✔ readr     2.1.4
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.0
    ## ✔ ggplot2   3.4.2     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.2     ✔ tidyr     1.3.0
    ## ✔ purrr     1.0.1     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

``` r
gg<-pressure %>%
  ggplot(aes(x=temperature, y=pressure)) + 
  geom_point()

gg
```

![](/images/unnamed-chunk-1-1.png) \## Include plotly

``` r
library(plotly)
```

    ## 
    ## Attaching package: 'plotly'

    ## The following object is masked from 'package:ggplot2':
    ## 
    ##     last_plot

    ## The following object is masked from 'package:stats':
    ## 
    ##     filter

    ## The following object is masked from 'package:graphics':
    ## 
    ##     layout

``` r
library(htmlwidgets)
p<-ggplotly(gg)
saveWidget(p, "p1.html", selfcontained = F, libdir = "lib")
```

``` r
htmltools::tags$iframe(
  src = "p1.html", 
  scrolling = "no", 
  seamless = "seamless",
  frameBorder = "0"
)
```

<iframe src="p1.html" scrolling="no" seamless="seamless" frameBorder="0"></iframe>

## test widgetframe

``` r
library(widgetframe)

frameWidget(p)
```

![](/images/unnamed-chunk-4-1.png)

## Include DT

``` r
library(DT)
dt <-  datatable(
  head(iris, 20), 
  options = list(
     columnDefs = list(list(className = 'dt-center', targets = 5)),
     pageLength = 5, lengthMenu = c(5, 10, 15, 20)),
  fillContainer = T)

frameWidget(dt, height = 350, width = '95%')
```

![](/images/unnamed-chunk-5-1.png)

## include leaflet

``` r
library(leaflet)
library(widgetframe)
l <- leaflet() %>% addTiles() %>% setView(0,0,1)
frameWidget(l, width='90%')
```

![](/images/leaflet-01-1.png)
