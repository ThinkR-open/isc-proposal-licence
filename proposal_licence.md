Licensing R Package - Guidelines and tools
================
Colin FAY & Miles McBain
2018-03-30

## The Challenge

Licensing is a vital part of Open Source. It provides guidelines for
interacting with a program, and for making code accessible and reusable
(or not). It provides a way to make your code open source, in a way you
want to share it, protecting how your code will be used and reused.

Though, licensing is a complex field: there are a lot of available
licences, and the choice is influenced by how you import and interact
with codes from other packages. It’s even harder when it comes to
combining licenses. For example:

> “By combining GPL-licensed code with code under any but the most
> unrestrictive licenses, the creator of the putative”new program" is
> imposing a restriction (compliance with the terms of that license)
> that is not present in the GPL License and which accordingly violates
> the GPL"

*Understanding Open Source and Free Software Licensing, Andrew M.
St. Laurent*

As [stated in Miles McBain
proposal](https://github.com/ropensci/unconf17/issues/32) for a unconf
workshop around this topic, a number of developers use licence without a
deep knowledge of what these licences precisely imply. And even if, a
lot of other questions can arise:

  - How do the dependencies to a package impact the choices when it
    comes to Licensing ?  
  - Can we use any license we want in an R package?
  - Can we use any license we want in R in general? R is *“is
    distributed under the terms of the GNU General Public License,
    either Version 2, June 1991 or Version 3, June 2007”*. How does this
    impact the code one is writing?
  - Do `depends`/`suggests` have the same impact on license choice?
  - What are one rights when one is contributing to a package?
  - What are the obligation of a package maintainer when it comes to
    changing the license of a package?
  - What do each licence really imply when using a package?  
  - How does a dependency license influence the licensing of a package?
  - What should be done if a package depends on two non-compatible open
    source licenses?
  - Are there global vs local states of open sources licenses?
  - How do license impact the writing of books/articles?

…

### Licensing and R

A quick dive into the CRAN package database can give us an overview of
how complex licensing and of how the community is making a lot of
different choices.

``` r
# Done on
Sys.Date()
```

    ## [1] "2018-10-08"

``` r
db <- tools::CRAN_package_db()
```

Let’s ask us a simple question: how many licences are currently used on
the CRAN?

``` r
# How many different licences? 
length(unique(db$License))
```

    ## [1] 155

Inside this list, various licences: GPL, Apache, LGPL, AGPL, CC0, MIT…

A lot appears to be a variation of the GPL license:

``` r
# How many GPL based licences ? 
length( unique( grep("GPL", db$License, value = TRUE) ) )
```

    ## [1] 83

## The plan

### Licensing: documentation & consulting

The first part of the plan is to gather documentation and notes about
current state of open source licences, and to decipher compatibility and
incompatibly elements inside these licenses.

This first steps will include:

  - gathering information from current state of open source
  - consulting one/several lawyers specialized in open source to gather
    advice about our findings.

### Licensing: guidelines

#### Bookdown

Once the first step is completed, we’ll write a bookdown containing all
the results from this finding.

This book will be distributed open source (under a license we will
choose based on our finding). The idea is to provide a simple but
comprehensive overview of open source licenses and how to use them in R.

### Licensing: tools

#### Pkg & App

The last step will be the development of a shiny app and a package that
will be able to give guidelines about the possibility of licensing for a
project.

The idea is to provide several features, included (but not limited to):

  - Giving the licenses one can use based on a package one want to use
    as a dependency
  - Parse a DESCRIPTION file to detect any licensing issue
  - Parse a package tar.gz to detect any licensing issue

## The Team

The research will be made by:

  - Colin Fay - ThinkR
  - Miles McBain - CSIRO

> About ThinkR: ThinkR is a french-based company that works with
> everything R and data science related. We focus on software
> engineering, package development and training.

> About CSIRO

The results will be hosted on GitHub, opened to external contributions.
The repo will have a Code of Conduct, and will be completed with a
contribution guide. Every contribution will be welcome, be it from a
beginner or a confirmed developer.

## Milestone

### Documentation

The documentation part will be a big part of the project.

> Estimated time: 3 to 4 months

### guidelines

> Estimated time: 3 to 4 months

### Tooling

> Estimated time: 1 to 2 months

### Communicating

A big part of the success of the project will be communication. We hope
that the community will grasp this opportunity to contribute and help,
either by providing inputs or feedback

## How Can The ISC Help

We are asking for a grant to support the working time spent to
investigate, gather information, to develop these tools and guidelines,
and to promote them. We plan on spending around ??? days a month on
these tools ( ??? days each). We are asking for the support of half of
these days from the RConsortium ( ??? ). The other half will be covered
by ThinkR & CSIRO, in its effort to support Open Source Software, by
freeing time for us to work on this project.

Below is a summary of our needs:

|          What | How long | How much |
| ------------: | -------: | -------: |
| Documentation | 4 months |      ??? |
|    Guidelines | 4 months |      ??? |
|       Tooling |  1 month |      ??? |

## Dissemination

We will publicise our work through several channels:

  - Blogposts on R related blogs (on ThinkR and others)
  - Article proposals on R and software engineering journals (R Journal,
    Journal of Statistical Software, …)

## Footnotes
