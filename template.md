---
title: "Learning Templates in R"
output:
  dcTemplate::dc_lesson_template:
    fig_width: 6
    fig_height: 6
    highlight: pygments
---


```{r knitr_init, echo = FALSE, cache = FALSE}
library(knitr)

## Global options
options(max.print = "75")
opts_chunk$set(cache = TRUE,
               prompt = FALSE,
               tidy = TRUE,
               comment = "> #",
               message = FALSE,
               warning = FALSE)
opts_knit$set(width = 75)
```

## Lesson Objectives

- To try out this template
- To make things look nice

## Lesson

Here we're learning about how to write a RMarkdown document
and then have it become a Markdown file that can be rendered
by Jekyll in github.

Here is a piece of a lesson

## Functions and their arguments

Functions are "canned scripts" that automate something complicated or convenient
or both.  Many functions are predefined, or become available when using the
function `library()` (more on that later). A function usually gets one or more
inputs called *arguments*. Functions often (but not always) return a *value*. A
typical example would be the function `sqrt()`. The input (the argument) must be
a number, and the return value (in fact, the output) is the square root of that
number. Executing a function ('running it') is called *calling* the function. An
example of a function call is:

`b <- sqrt(a)`

Here, the value of `a` is given to the `sqrt()` function, the `sqrt()` function
calculates the square root, and returns the value which is then assigned to
variable `b`. This function is very simple, because it takes just one
argument. 

The return 'value' of a function need not be numerical (like that of `sqrt()`),
and it also does not need to be a single item: it can be a set of things, or
even a data set. We'll see that when we read data files in to R. 

Arguments can be anything, not only numbers or filenames, but also other
objects. Exactly what each argument means differs per function, and must be
looked up in the documentation (see below). If an argument alters the way the
function operates, such as whether to ignore 'bad values', such an argument is
sometimes called an *option*.

Most functions can take several arguments, but many have so-called *defaults*.
If you don't specify such an argument when calling the function, the function
itself will fall back on using the *default*. This is a standard value that the
author of the function specified as being "good enough in standard cases". An
example would be what symbol to use in a plot. However, if you want something
specific, simply change the argument yourself with a value of your choice.

Let's try a function that can take multiple arguments `round`.

```{r, results='show'}
round(3.14159)
```

We can see that we get `3`. That's because the default is to round
to the nearest whole number. If we want more digits we can see 
how to do that by getting information about the `round` function.
We can use `args(round)` or look at the
help for this function using `?round`.

```{r, results='show'}
args(round)
```

```{r, eval=FALSE}
?round
```


We see that if we want a different number of digits, we can 
type `digits=2` or however many we want.

```{r, results='show'}
round(3.14159, digits=2)
```

If you provide the arguments in the exact same order as they are defined you don't have to name them:

```{r, results='show'}
round(3.14159, 2)
```

However, it's usually not recommended practice because it's a lot of remembering
to do, and if you share your code with others that includes less known functions
it makes your code difficult to read. (It's however OK to not include the names
of the arguments for basic functions like `mean`, `min`, etc...)

Another advantage of naming arguments, is that the order doesn't matter.
This is useful when there start to be more arguments. 


## Organizing your working directory

You should separate the original data (raw data) from intermediate datasets that
you may create for the need of a particular analysis. For instance, you may want
to create a `data/` directory within your working directory that stores the raw
data, and have a `data_output/` directory for intermediate datasets and a
`figure_output/` directory for the plots you will generate.




