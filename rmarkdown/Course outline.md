# Course outline

Based on:
https://rstudio-education.github.io/hopr/
https://melbournebioinformatics.github.io/r-intro-biologists/intro_r_biologists.html#Session_Info


## The Basics

* What is R?
* How do I use it?
    - console vs. IDE
* What are the basic building blocks?
    - the R syntax (running code on single lines. spaces, comas, brackets, $, case sensitive)
    - Objects (Vectors!!, lists (many vectors) , matrix (a table of vectors) and many more)
    - Types of vectors (i.e. what can you store in a vector?) (character, numeric [integer, double], factor, logical, complex (e.g. a fucntion) )
        - ways to make sequences (1:10, seq(1:10), sample(n=10))
    - Operators
    - Functions (arguments)
* What are packages/libraries?
* Common R errors
    - Case sensitivity. In R, as in other programming languages, case sensitivity is important. ?install.packages is different to ?Install.packages.
    - Missing commas
    - Mismatched parentheses or brackets
    - Not quoting file paths
    - Not finishing a command so seeing “+” in the console. If you need to, you can press ESC to cancel the command.



## R markdown
* Components of a markdown file
    - yaml header
    - formatted text
    - code chunks
* 'knitting' your markdown file

## Your very first R project [plotting data]
* setting working directory
* import data, manipulate data and plot, export data and plot.
* Plot sepal-petal data? Card deal/shuffle functions

## Manipulating data with the Tidyverse

- Combine the following functions into a single project:
* pipes and workflows
* select, filter, arrange
* mutate
* group and summarize
* join
* pivot

## Data vizualization

* GGplot and geoms (pie, bar, box, histogram, scatter, lines, simple maps)
* colouring by category
* facetting
* interactive plots with plotly

## Basic Statistics

https://www.statmethods.net/stats/descriptives.html

* descriptive statitics: mean, median, sum, quartiles, sd
* Exploratory plots (ggpairs)
* t-test and ANOVA
* linear models

## Where to get help?

* Stack overflow
* ChatGPT


## Bring your own data
* bring your own data

## Datasets

https://datacarpentry.org/semester-biology/materials/datasets/
https://stat.ethz.ch/R-manual/R-devel/library/datasets/html/00Index.html



## other possible subjects
* loops and conditionals (if, else)
