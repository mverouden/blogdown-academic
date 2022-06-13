---
## The title of your page
title: 'R installation on Linux'
## An optional subtitle that will be displayed under the title 
subtitle: ''

## A one-sentence summary of the content on your page. 
##   The summary can be shown on the homepage and can also benefit your search
##   engine ranking.
summary: 'Instructions on how to install R on Linux.'

## Add the short URL slug containing keywords
slug: r-installation-linux

## Display the authors of the page and link to their user profiles if they exist.
authors:
  - admin

## Tagging your content helps users to discover similar content on your site. 
##   Tags can improve search relevancy and are displayed after the page content
##   and also in the Tag Cloud widget.
tags:
  - Installation
  - R
  - Linux

##   Categories can improve search relevancy and display at the top of a page
##   alongside a page’s metadata.
categories:
  - R
  - Linux

## The RFC 3339 date that the page was published. 
date: '2022-06-13T11:12:16+0200'
##   Dates can now be hidden from pages by adding show_date: false in page front
##   matter or by automatically applying it to all pages in a collection using
##   Hugo's cascade:>show_date: false in the _index.md file.
show_date: true

## The RFC 3339 date that the page was published. 
##   You only need to specify this option if you wish to set date  in the future
##   but publish the page now, as is the case for publishing a journal article
##   that is to appear in a journal, etc.
# publishDate: '2020-11-03T00:00:00Z'

## The RFC 3339 date that the page was last modified. 
##   If using Git, enable enableGitInfo in `config.yaml` to have  the page
##   modification date automatically updated, rather than manually specifying
##   lastmod.
lastmod: '2022-06-13T11:12:16+0200'

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
At Wageningen University & Research the Linux Operating System is supported on a best effort principle, meaning that it is supported as far as the knowledge of Facilities and Services Information Technology (FB-IT) reaches. FB-IT is supported by their colleagues maintaining the High Performance Computing Cluster Anunna, who have a lot of knowledge about the Linux Operating System, because it's the Operating System used by Anunna. <!-- and there is a support mail address: <a href="mailto:linux.beheer@wur.nl">linux.beheer AT wur.nl</a>, where support questions can be sent.-->

On the other hand Linux users are generally users, who are very independent and know how to search for and implement solutions themselves. Being one of those Linux users within WUR myself I want to share in this post, how I have installed R on my Linux Systems within Wageningen University & Research.

{{% callout note %}}
This post will show how to install R on a Linux desk- or laptop computer.

Two types of Linux Operating Systems are described:

1. Debian based, e.g. LMDE 5 Elsie (based on Debian 11 Bullseye)
2. Ubuntu based, e.g. Linux Mint 20.3 (based on Ubuntu 20.04.4 LTS a.k.a. Focal Fossa)
{{% /callout %}}

## Installation R

### Debian based Linux Operating System

The installation procedure described here, combines information as provided on https://cloud.r-project.org/bin/linux/debian/. At the time of writing this post the described procedure installs R version 4.2.0 (nicknamed: Vigorous Calisthenics), under the assumption that the Linux Operating System is based on Debian 11 Bullseye.

1. Open a terminal (CTRL+ALT+T) and log in as administrator using the console command:
```sh
sudo -i
```

2. Fetch and import the current key using the following command:
```sh
apt-key adv --keyserver keyserver.ubuntu.com --recv-key '95C0FAF38DB3CCAD0C080A7BDC78B2DDEABC47B7'
```

3. Add Debian bullseye repository to the software sources using the command:
```sh
add-apt-repository "deb http://cloud.r-project.org/bin/linux/debian bullseye-cran40/"
```

4. Update the package information from all configured sources:
```sh
apt update
```

5. Fully install R with dependencies:
```sh
apt install r-base libatlas3-base libopenblas-base r-cran-littler r-cran-coda r-doc-info r-doc-pdf python3-rpy2 r-mathlib
```

6. Exit out of administrator mode using the `exit` command.

{{% callout note %}}
Congratulations, you can now use R within a terminal on your Debian based Linux Operating System!
{{% /callout %}}

### Ubuntu based Linux Operating System

The installation procedure described here, combines information as provided on https://cloud.r-project.org/bin/linux/ubuntu/fullREADME.html. At the time of writing this post the described procedure installs R version 4.2.0 (nicknamed: Vigorous Calisthenics), under the assumption that the Linux Operating System is based on Ubuntu 20.04.4 LTS Focal Fossa.

1. Open a terminal (CTRL+ALT+T) and log in as administrator using the console command:
```sh
sudo -i
```

2. Fetch and import the current key using the following command:
```sh
apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
```

3. Add Ubuntu Focal Fossa repository to the software sources using the command:
```sh
add-apt-repository "deb https://cloud.r-project.org/bin/linux/ubuntu focal-cran40/"
```

4. Update the package information from all configured sources:
```sh
apt update
```

5. Fully install R with dependencies:
```sh
apt install r-base r-cran-littler r-cran-rodbc r-doc-info r-doc-pdf r-mathlib elpa-ess ess jags littler python3-rpy2
```

6. Exit out of administrator mode using the `exit` command.

{{% callout note %}}
Congratulations, you can now use R within a terminal on your Ubuntu based Linux Operating System!
{{% /callout %}}
