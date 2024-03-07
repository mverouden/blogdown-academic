---
## The title of your page
title: "Rtools installation on a Windows 10/11 or a WURclient computer"
## An optional subtitle that will be displayed under the title 
subtitle: ''

## A one-sentence summary of the content on your page. 
##   The summary can be shown on the homepage and can also benefit your search
##   engine ranking.
summary: 'Instructions on how to install Rtools on a Windows 10/11 or a WURclient computer.'

## Add the short URL slug containing keywords
slug: rtools-installation

## Display the authors of the page and link to their user profiles if they exist.
authors:
  - admin

## Tagging your content helps users to discover similar content on your site. 
##   Tags can improve search relevancy and are displayed after the page content
##   and also in the Tag Cloud widget.
tags:
  - Installation
  - R
  - Rtools
  - Windows 10
  - Windows 11
  - WURclient

##   Categories can improve search relevancy and display at the top of a page
##   alongside a page’s metadata.
categories:
  - R
  - WUR
  - WURclient
  - Windows 10
  - Windows 11

## The RFC 3339 date that the page was published. 
date: '2022-07-05T11:15:44+0200'
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
lastmod: '2022-07-05T11:15:45+0200'

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
Many people are able to use R, without ever having the need to compile from source and, therefore, the need to install Rtools. However, if you want to do package development, compile from source, or use packages like **rstan** or **cmdstanr**, you will definitely need to install Rtools.

In this post the installation procedure for Rtools will be given step wise. It will work for both regular Windows 10/11 computers as well as WURclient computers.

A WURclient desktop or laptop at Wageningen University & Research is not a standard Windows 10 computer. WURclients use Windows 10 Enterprise, which has been modified by Facilities and Services Information Technology (FB-IT) among others with respect to installation rights for security reasons.

{{% callout note %}}
This post will show how to install Rtools on a **privately owned** running Windows 10/11, or a **WURclient** desktop or laptop computer, where the user possesses <u>**POWER USER RIGHTS**</u>.

The only difference is how the installer for Rtools is started.
{{% /callout %}}

## Requirement for and Download of Rtools

### Requirement

Prior requirement for using Rtools:

- [x] R properly installed:
  - [x] [R installed on Windows 10/11](/post/2020/04/06/r-installation-windows-10/)
  - [x] R installed on a WURclient via Software Center, or
  - [x] [R installed on a WURclient using a custom installation ](/post/2021/01/24/r-installation-wurclient/)

Without having R installed on your desktop or laptop computer it makes no sense to install RTools. The software Rtools provides, as the name suggests, tools (compilers, and such) for use within R.

### Download

Rtools can be downloaded for the following webpage: https://cran.r-project.org/bin/windows/Rtools/

Download the correct vesion, which matches the version of R installed on your desktop or laptop computer.

For R version 4.3.0 and above the installer for Rtools can be downloaded directly from this link: [{{< icon name="download" pack="fas" >}} Rtools43 installer (ca. 422 MB, 64-bit).](https://cloud.r-project.org/bin/windows/Rtools/rtools43/files/rtools43-5958-5975.exe)

## Installation Rtools
The screenshots below are for the installation of Rtools42 and have not been updated, because the procedure for Rtool43 remains the same.

1. Open a File Explorer window (keyboard shortcut: &#129695; + E) and navigate to your downloads folder.

2. On a Windows 10/11 computer start the downloaded Rtools installer. For a **WURclient** computer right-click the downloaded Rtools installer and select select 'WUR - Run with administrative rights' (see below in [Figure 1](#figure-start_installer_wurclient)).

{{< figure src="rtools/00-installer-admin-rights.png" caption="Start Rtools installer on a WURclient." numbered="true" id="start_installer_wurclient" >}}

3. The Rtools installer will open with the Select Destination Location window as displayed below in [Figure 2](#figure-select_destination_location). **Do not change the destination location, leave the default suggested value!** Click ‘Next’ to continue.

{{< figure src="rtools/01-select-destination-location.png" caption="Select Rtools destination location." numbered="true" id="select_destination_location" >}}

4. The installer will next show the Select Additional Tasks window, as show in [Figure 3](#figure-select_additional_tasks). Make sure that both boxes are ticked and click the ‘Next’ button to continue.

{{< figure src="rtools/02-select-additional-tasks.png" caption="Select Rtools additional tasks." numbered="true" id="select_additional_tasks" >}}

5. Now the installer will present a window, as displayed below in [Figure 4](#figure-ready_to_install), with the selected installation options. Click the ‘Install’ button to start the installation or select ‘Back’ to modify the installer options.

{{< figure src="rtools/03-ready-2-install.png" caption="Rtools ready to install overview." numbered="true" id="ready_to_install" >}}

6. Once the installer has completed, [Figure 5](#figure-finish_setup) will be shown. Click the ‘Finish’ button to complete the installation.

{{< figure src="rtools/04-completing-rtools-setup-wizard.png" caption="Finish the Rtools installation." numbered="true" id="finish_setup" >}}

## Check the Installation

For Rtools 4.3 there is an easy way to check, that the installation of Rtools was successful.

1. Open R (either RGui or RStudio)
2. Execute the following command: `Sys.which("make")`

When R returns `"C:\\rtools43\\usr\\bin\\make.exe"`, you know that Rtools was successfully installed.

{{% callout warning %}}
For Rtools 4.0 the returned path will be empty.

This does not mean that the installation was not successful. Just that Rtools was not automatically added to the PATH environment variable.

If you wish to add Rtools to the PATH environment variable, please follow the instructions on https://cran.r-project.org/bin/windows/Rtools/rtools40.html
{{% /callout %}}
