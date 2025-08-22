---
## The title of your page
title: "RStan installation on a Windows 10/11 or a WURclient computer"
## An optional subtitle that will be displayed under the title 
subtitle: ''

## A one-sentence summary of the content on your page. 
##   The summary can be shown on the homepage and can also benefit your search
##   engine ranking.
summary: 'Instructions on how to install RStan on Windows 10/11.'

## Add the short URL slug containing keywords
slug: rstan-installation

## Display the authors of the page and link to their user profiles if they exist.
authors:
  - admin

## Tagging your content helps users to discover similar content on your site. 
##   Tags can improve search relevancy and are displayed after the page content
##   and also in the Tag Cloud widget.
tags:
  - Installation
  - R
  - RStan
  - Windows 10
  - Windows 11
  - WURclient

##   Categories can improve search relevancy and display at the top of a page
##   alongside a page’s metadata.
categories:
  - R
  - RStan
  - Windows 10
  - Windows 11
  - WURclient
  - WUR
  
## The RFC 3339 date that the page was published. 
date: '2023-08-27T16:19:00+0200'
##   Dates can now be hidden from pages by adding show_date: false in page front
##   matter or by automatically applying it to all pages in a collection using
##   Hugo's cascade:>show_date: false in the _index.md file.
show_date: true

## The RFC 3339 date that the page was published. 
##   You only need to specify this option if you wish to set date  in the future
##   but publish the page now, as is the case for publishing a journal article
##   that is to appear in a journal, etc.
# publishDate: '2023-08-27T16:19:00+0200'

## The RFC 3339 date that the page was last modified. 
##   If using Git, enable enableGitInfo in `config.yaml` to have  the page
##   modification date automatically updated, rather than manually specifying
##   lastmod.
lastmod: '2023-08-27T16:19:00+0200'

## By setting `featured: true`, a page can be displayed in the Featured widget. 
##   This is useful for sticky, announcement blog posts or selected publications,
##   etc.
featured: false

## By setting `draft: true`, only you will see your page  when you preview your
## site locally on your computer.
draft: false

## Featured image
##   To use, add an image named `featured.jpg/png` to your page's folder.
##   Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
##   Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right,
##   BottomLeft, Bottom, BottomRight
image:
  caption: 'Image credit: [**_Panos Sakalakis_ on Unsplash**](https://unsplash.com/photos/AwDVMJKMjlU)'
  focal_point: 'Center'
  # placement: 2
  preview_only: false
  # alt_text: An optional description of the image for screen readers.

## Projects
##   Associate this post with one or more of your projects.
##   Simply enter your project's folder or file name without extension.
##   E.g. `projects = ["internal-project"]` references
##   `content/project/internal-project/index.md`.
##   Otherwise, set `projects = []`.
projects: []

## Page resources
##   Buttons can be generated in the page header to link to associated resources.
##   The example below shows how to create a Twitter link for a project and 
##   how to create a link to a post that was originally published on Medium:
# links:
#   - icon: twitter
#     icon_pack: fab
#     name: Follow
#     url: 'https://twitter.com/Herb_hewang'
#   - icon_pack: fab
#     icon: medium
#     name: Originally published on Medium
#     url: 'https://medium.com'   # (required)

## The following parameters can be added to the front matter of 
##   a page (such as a blog post) to control its features:
##
## Show estimated reading time?
reading_time: true
## Show social sharing links?
share: true
## Show author profile?
profile: true
## Allow visitors to comment?
## Supported by the Page, Post, and Docs content types.
commentable: false
## Allow visitors to edit the page?
## Supported by the Page, Post, and Docs content types.
editable: false

## To enable LaTeX math rendering for a page, you should include `math: true` in
## the page’s front matter.
##   Not necessary if globally enabled `math.enable: true` in
##   `config/_default/params.yaml`
math: true

## Enable a Markdown extension for diagrams by toggling the diagram
##   option in your `config/_default/params.toml` file or by adding
##   `diagram: true` to your page front matter.
diagram: true
---

{{% toc %}}

## Motivation
Whether working or studying everybody uses various sorts and types of software on their computer. Students taking [Statistical Courses, as taught by the Mathematical and Statistical Methods group at Wageningen University & Research](https://www.wur.nl/en/Research-Results/Research-Institutes/plant-research/biometris/Education/BSc-and-Master-Courses.htm), will most likely use R. Students enrolled in [MAT34806 Bayesian Data Analysis](https://wur.osiris-student.nl/#/onderwijscatalogus/extern/cursus?cursuscode=MAT34806&collegejaar=huidig) will use RStan as well as basic R. Therefore, they will need to install RStan.

RStan is an implementation of [Stan](https://mc-stan.org/) in [R](https://www.r-project.org/). Stan is a state-of-the-art platform for statistical modeling and high-performance statistical computation. Thousands of users rely on Stan for statistical modeling, data analysis, and prediction in the social, biological, and physical sciences, engineering, and business.

Users specify log density functions in Stan’s probabilistic programming language and get:

- full Bayesian statistical inference with MCMC sampling (NUTS, HMC)

- approximate Bayesian inference with variational inference (ADVI)

- penalized maximum likelihood estimation with optimization (L-BFGS)

Stan’s math library provides differentiable probability functions & linear algebra (C++ autodiff). Additional R packages provide expression-based linear modeling, posterior visualization, and leave-one-out cross-validation.

{{% callout note %}}
This post will show how to install Rtools on a **privately owned** computer running Windows 10/11, or a **WURclient** desktop or laptop computer.
{{% /callout %}}

## Requirements for RStan installation

Prior requirements for installing RStan:

- [x] R properly installed:
  - [x] [R installed on Windows 10/11](/post/2020/04/06/r-installation-windows-10/)
  - [x] R installed on a WURclient via Software Center, or
  - [x] [R installed on a WURclient using a custom installation](/post/2021/01/24/r-installation-wurclient/)

- [x] [Rtools installed on a Windows 10/11 or a WURclient computer](/post/2022/07/05/rtools-installation/)

Without having R and Rtools installed on your desktop or laptop computer, it makes no sense to try to install RStan. RStan needs to be able to compile from source within R, making R and Rtools indispensable.

Not required, however, highly recommended:

- [ ] RStudio installed:

  - [ ] [RStudio installed on Windows 10/11](/post/2020/04/13/rstudio-installation-on-windows-10/)
  - [ ] RStudio installed on a WURclient via Software Center, or
  - [ ] [RStudio installed on a WURclient using a custom installation](/post/2021/06/17/rstudio-installation-wurclient/)

## Installation

The RStan installation, described here, assumes usage of **R version 4.2.x or above**. It uses the latest versions of the <a href="https://cran.r-project.org/web/packages/rstan/index.html" target="_blank">**rstan**</a> and  <a href="https://cran.r-project.org/web/packages/StanHeaders/index.html" target="_blank">**StanHeaders**</a> packages available on CRAN.<!--It uses the latest development version (v2.32.x) of the RStan package, because of incompatibility of the current RStan package on CRAN (v2.21.x) for R versions above v4.2.x, as mentioned on [The Stan Blog: Stan & R 4.2 on Windows](https://blog.mc-stan.org/2022/04/26/stan-r-4-2-on-windows/).-->

To install RStan:

1. Start either **RStudio**, or the default **R GUI**. RStudio being the recommended interface!

2. Remove, if present, the existing installation of the packages `StanHeaders` and `rstan` by executing at the R prompt:

```r
remove.packages(pkgs = c("StanHeaders", "rstan"))
```

3. Install the latest on CRAN available version of `StanHeaders` and `rstan` by executing at the R prompt:

```r
install.packages(pkgs = c("StanHeaders","rstan"),
                repos = c("https://cloud.r-project.org",
                getOption("repos")))
```
<!--
3. Install the latest development version of `StanHeaders` and `rstan` by executing at the R prompt:

```r
install.packages(pkgs = c("StanHeaders","rstan"),
                repos = c("https://mc-stan.org/r-packages/",
                getOption("repos")))
```

-->
{{% callout note %}}
Congratulations, :satisfied:, you now have RStan installed on your personal Windows 10/11 or WURclient computer!
{{% /callout %}}

## Verifying the RStan installation

To verify the RStan installation run the RStan example/test model at the R prompt:

```r
# Load the RStan library
library(rstan)
# Start up settings
options(mc.cores = parallel::detectCores())
rstan_options(auto_write = TRUE)
rstan_options(threads_per_chain = 1)
# Run example
example(stan_model, package = "rstan", run.dontrun = TRUE)
```
The model should then compile and sample.

If the example model fails with the error:

```r
Error in compileCode(f, code, language = language, verbose = verbose) : 
  C:\rtools43\x86_64-w64-mingw32.static.posix\bin/ld.exe: file327c377a3dae.o:file327c377a3dae.cpp:(.text$_ZN3tbb8internal26task_scheduler_observer_v3D0Ev[_ZN3tbb8internal26task_scheduler_observer_v3D0Ev]+0x1d): undefined reference to `tbb::internal::task_scheduler_observer_v3::observe(bool)'C:\rtools42\x86_64-w64-mingw32.static.posix\bin/ld.exe: file327c377a3dae.o:file327c377a3dae.cpp:(.text$_ZN3tbb10interface623task_scheduler_observerD1Ev[_ZN3tbb10interface623task_scheduler_observerD1Ev]+0x1d): undefined reference to `tbb::internal::task_scheduler_observer_v3::observe(bool)'C:\rtools42\x86_64-w64-mingw32.static.posix\bin/ld.exe: file327c377a3dae.o:file327c377a3dae.cpp:(.text$_ZN3tbb10interface623task_scheduler_observerD1Ev[_ZN3tbb10interface623task_scheduler_observerD1Ev]+0x3a): undefined reference to `tbb::internal::task_scheduler_observer_v3::observe(bool)'C:\rtools42\x86_64-w64-mingw32.static.posix\bin/ld.exe: file327c377a3dae.o:file327c377a3dae.cpp:(.text$_ZN3tbb10interface
Error in sink(type = "output") : invalid connection
```

Verify that the packages `StanHeaders` and `rstan` installed are of version 2.32.x or above. Executing the following commands will show the installed versions:

```r
packageVersion(pkg = "StanHeaders")
packageVersion(pkg = "rstan")
```

When the installed versions are lower than version 2.32.x, then repeat steps 2. and 3. as described in the section [Installation](#installation).

### Failed with error: 'there is no package called 'rstudioapi''

When the verification of the Rstan installation fails with:
```
Loading required namespace: rstudioapi
Failed with error:  ‘there is no package called ‘rstudioapi’’
Error in .local(object, ...) : 
  must install the rstudioapi package when using RStan in parallel via RStudio
```

The last line tells exactly what to do to fix the problem. Install the `rstudioapi` package using:

```r
install.packages("rstudioapi")
```

Retry to verifying the RStan installation as describe above. Now it should work!

## Loading the package
The package name is `rstan` (all lowercase), to load the package execute:

```r
library(rstan) # observe startup messages
```

As the start up message says, when using `rstan` locally on a multi-core machine and the system has plenty of RAM to estimate the model in parallel, at this point execute at the R prompt:

```r
options(mc.cores = parallel::detectCores())
```

In addition, execute the second start up message at the R prompt:
```r
rstan_options(auto_write = TRUE)
```
which allows to automatically save a bare version of a compiled Stan program to the hard disk so that it does not need to be recompiled (unless after changing the program). These commands will need to be run, each time the `rstan` library is loaded load in R.

Finally, when using Windows as operating system, there will be a third startup message saying **not** to use `--march=native` compiler flag. This warning can be ignored, if the steps above have been followed and a `Makevars.win` file on your system does not contain this flag. When the file name `Makevars.win` does not ring any bells, this probably means it doesn't exist in your system.

## Installing the **`brms`** package

In the course [MAT34806 Bayesian Data Analysis](https://wur.osiris-student.nl/#/onderwijscatalogus/extern/cursus?cursuscode=MAT34806&collegejaar=huidig) the `brms` package will be used. This package extends RStan for Bayesian regression modeling. The package abbreviation `brms` stands for Bayesian Regression Models using 'Stan'.

When the installation of RStan has been completed successfully, install the `brms` package by executing at the R prompt the following command:

```r
install.packages(pkgs = "brms")
```
