---
## The title of your page
title: 'R Commander installation in R on Linux'
## An optional subtitle that will be displayed under the title 
subtitle: ''

## A one-sentence summary of the content on your page. 
##   The summary can be shown on the homepage and can also benefit your search
##   engine ranking.
summary: 'Instructions on how to install R Commander in R on Linux.'

## Add the short URL slug containing keywords
slug: r-commander-installation-linux

## Display the authors of the page and link to their user profiles if they exist.
authors:
  - admin

## Tagging your content helps users to discover similar content on your site. 
##   Tags can improve search relevancy and are displayed after the page content
##   and also in the Tag Cloud widget.
tags:
  - Installation
  - R Commander
  - R
  - Linux

##   Categories can improve search relevancy and display at the top of a page
##   alongside a page’s metadata.
categories:
  - R
  - Linux

## The RFC 3339 date that the page was published. 
date: '2023-09-06T09:00:00+0200'
##   Dates can now be hidden from pages by adding show_date: false in page front
##   matter or by automatically applying it to all pages in a collection using
##   Hugo's cascade:>show_date: false in the _index.md file.
show_date: true

## The RFC 3339 date that the page was published. 
##   You only need to specify this option if you wish to set date  in the future
##   but publish the page now, as is the case for publishing a journal article
##   that is to appear in a journal, etc.
# publishDate: '2023-09-06T09:00:00Z'

## The RFC 3339 date that the page was last modified. 
##   If using Git, enable enableGitInfo in `config.yaml` to have  the page
##   modification date automatically updated, rather than manually specifying
##   lastmod.
lastmod: '2023-09-06T12:00:00+0200'

## Cacommentable: false
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
  # placement: 1
  caption: 'Image credit: [**_Unknown_ on Google**](https://www.google.com/)'
  focal_point: 'Center'
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
---

{{% toc %}}

## Motivation
At Wageningen University & Research the Linux Operating System is supported on a best effort principle, meaning that it is supported as far as the knowledge of Facilities and Services Information Technology (FB-IT) reaches. FB-IT is supported by their colleagues maintaining the High Performance Computing Cluster Anunna, who have a lot of knowledge about the Linux Operating System, because it's the Operating System used by Anunna. <!-- and there is a support mail address: <a href="mailto:linux.beheer@wur.nl">linux.beheer AT wur.nl</a>, where support questions can be sent.-->

On the other hand Linux users are generally users, who are very independent and know how to search for and implement solutions themselves. Being one of those Linux users within WUR myself I want to share in this post, how I have installed R Commander in R on my Linux Systems within Wageningen University & Research.

{{% callout note %}}
This post will show how to install R Commander in R on a Linux desk- or laptop computer.
{{% /callout %}}

## Installation R Commander

Prior requirement for installing R Commander on Linux:

- [x] [R installed on Linux](/post/2022/06/13/r-installation-linux/)

To be able to install R Commander you will need to have R installed first. If you haven't done so already, please read R installation on Linux (use the link above to go to that specific post) before continuing with this post.

### Tcl/Tk for R Commander

R Commmander has been programmed in Tcl (Tool Command Language) and uses Tk as a graphical user interface toolkit. To be able to use R Commander correctly on Linux, software needs to installed that enables the use of Tcl/Tk.

To install Tcl/Tk on your Linux system perform the following steps:

1. Open a terminal (CTRL+ALT+T) and log in as administrator using the console command:
```sh
sudo -i
```

2. Install the required software for Tcl/Tk execute at the console prompt:
```sh
apt install tcl tk tk-table
```

3. Exit out of administrator mode using the `exit` command. Do not close the terminal application!

### Installation of CRAN packages for R Commander

R Commander can be started from within R, when all required packages are installed from the Comprehensive R Archinve Network [(CRAN)](https://cloud.r-project.org/). To install the packages perform the following steps in the open terminal:

1. Start R by executing in at the console prompt: `R`

2. At the R console prompt execute the following command:
```r
install.packages("Rcmdr")
```

{{% callout warning %}}
When asked to select a CRAN mirror, pick the "0-cloud" mirror. This will always select the CRAN mirror nearest to your location.
{{% /callout %}}

3. Additional required packages can be installed using the `install.packages()` function. For example to add R Commander support for the Statistical Analysis and Data Display: Heiberger and Holland package use:
```r
install.packages("RcmdrPlugin.HH")
```

{{% callout note %}}
Congratulations, you can now use R Commander in R on your Linux Operating System!
{{% /callout %}}

## First time use of R Commander

{{% callout warning %}}
**When using R Commander for the first time additional packages required for R Commander to work correctly will need to be installed. Allow the installation to be able to work smoothly without errors!**
{{% /callout %}}

To start R Commander from the R Console, type the command `library(Rcmdr)` behind the prompt and execute.

## Restarting R Commander
In case R Commander crashes while using it, you will need to resart it. However, in the R Console or in the active terminal console currently running R, the `library(Rcmdr)` command will not restart R Commander.

The reason is, that the R Commander package is still loaded and first needs to be detached. To detach the R Commander package execute the following command:
```R
detach("package:Rcmdr", unload = TRUE)
```

When a plugin has been loaded, e.g, `RcmdrPlugin.HH` a warning message will be shown at the R prompt:
```r
Warning message:
‘Rcmdr’ namespace cannot be unloaded:
  namespace ‘Rcmdr’ is imported by ‘RcmdrPlugin.HH’ so cannot be unloaded
```

To be able to restart R Commander, first the plugin needs to be detached. Execute for example:
```r
detach("package:RcmdrPlugin.HH", unload = TRUE)
```
Next re-execute at the R console prompt:
```R
detach("package:Rcmdr", unload = TRUE)
```

Now R Commander can be restarted by using the `library(Rcmdr)` command as before.
