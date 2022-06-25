---
## The title of your page
title: 'Rtools installation on a Windows 10 or a WURclient computer'
## An optional subtitle that will be displayed under the title 
subtitle: ''

## A one-sentence summary of the content on your page. 
##   The summary can be shown on the homepage and can also benefit your search
##   engine ranking.
summary: 'Instructions on how to install Rtools on a Windows 10 or a WURclient computer.'

## Add the short URL slug containing keywords
slug: rtools-installation-w10-wurclient

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
  - WURclient

##   Categories can improve search relevancy and display at the top of a page
##   alongside a page’s metadata.
categories:
  - R
  - WUR
  - WURclient
  - Windows 10

## The RFC 3339 date that the page was published. 
date: '2022-06-14T19:08:21+0200'
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
lastmod: '2022-06-14T19:10:21+0200'

## By setting `featured: true`, a page can be displayed in the Featured widget. 
##   This is useful for sticky, announcement blog posts or selected publications,
##   etc.
featured: false

## By setting `draft: true`, only you will see your page  when you preview your
## site locally on your computer.
draft: true

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

In this post the installation procedure for Rtools will be given step wise. It will work for both regular Windows 10 computers as well as WURclient computers.

A WURclient desktop or laptop at Wageningen University & Research is not a standard Windows 10 computer. WURclients use Windows 10 Enterprise, which has been modified by Facilities and Services Information Technology (FB-IT) among others with respect to installation rights for security reasons.

{{% callout note %}}
This post will show how to install Rtools on a **privately owned** running Windows 10, or a **WURclient** desktop or laptop computer.

The only difference is how the installer for Rtools is started.
{{% /callout %}}

## Requirement for and Download of Rtools

### Requirement

Prior requirement for using Rtools:

- [x] R properly installed:
  - [x] [R installed on Windows 10](/post/2020/04/06/r-installation-windows-10/)
  - [x] R installed on a WURclient via Software Center, or
  - [x] [R installed on a WURclient using a custom installation ](/post/2021/01/24/r-installation-wurclient/)

Without having R installed on your desktop or laptop computer it makes no sense to install RTools. The software Rtools provides, as the name suggests, tools (compilers, and such) to be used within R.

### Download

Rtools can be downloaded for the following webpage: https://cran.r-project.org/bin/windows/Rtools/

Download the correct vesion, which matches the version of R installed on your desktop or laptop computer.

For R version 4.2.0 and above the installer for Rtools can be downloaded directly from this link: [{{< icon name="download" pack="fas" >}} Rtools42 installer (ca. 467 MB, 64-bit).](https://cran.r-project.org/bin/windows/Rtools/rtools42/files/rtools42-5253-5107.exe)

To be able to install R Commander you will need to have R installed first. If you haven't done so already, please first install R on your Windows 10 computer (use the link above to go to that specific post).

This post was originally based on R version 3.6.3. For newer versions of R the steps described are the same, only some screens you will see during your installation will display a higher version number of R compared to the screenshots in this post.

1. Start `R x64 4.2.0` from the ‘R’ folder in the ‘Start Menu’ as displayed below in [Figure 1](#figure-startmenu_r).

{{< figure src="r-commander-windows/startmenu-r.png" caption="Start Menu R x64" numbered="true" id="startmenu_r" >}}

2. The R GUI (graphical user interface) will open and the cursor will be ready for input behind the prompt, as indicated by the `>` sign. Use the mouse pointer and navigate to the top menu and select ‘Packages’ > ‘Install Package(s)...’ as shown in [Figure 2](#figure-install_packages_rgui).

{{< figure src="r-commander-windows/install-packages-r-gui.png" caption="R GUI Install Packages" numbered="true" id="install_packages_rgui" >}}

3. Now a CRAN (Comprehensive R Archive Network) mirror needs to be selected, from which packages will be installed. Select, as shown below in [Figure 3](#figure-select_cran_mirror), the top one ‘0-Cloud [https]’. This to make sure, that always the nearest CRAN mirror will be used no matter where you will be on the globe :earth_africa:. Click on the ‘OK’ button to confirm the selection.

{{< figure src="r-commander-windows/select-cran-mirror.png" caption="R GUI Select CRAN Mirror" numbered="true" id="select_cran_mirror" >}}

4. After the CRAN mirror selection a list of available packages will appear. Scroll down to find the `Rcmdr` package and click it to select. As shown below in [Figure 4](#figure-install_rcmdr_package) the package will turn blue, when selected. Confirm the installation by clicking the ‘OK’ button. Now a lot will happen in your display while the `Rcmdr` pacakage and its dependencies are being installed.

{{< figure src="r-commander-windows/install-package-Rcmdr.png" caption="R GUI Select the Rcmdr package to be installed." numbered="true" id="install_rcmdr_package" >}}

5. Repeat step 4. for installing the `RcmdrPlugin.HH` package. This plugin is required <!--in MAT-15403 Statistics 2--> to be able to do assignments about Simple Linear Regression.

{{% callout note %}}
Once the installation of the `RcmdrPlugin.HH` package has finished, you are ready :satisfied: to start R 4.2.0 and use R Commander.
{{% /callout %}}

{{% callout warning %}}
**When using R Commander for the first time additional packages, required for R Commander to work correctly, will need to be installed. Allow the installation to be able to work smoothly without errors!**
{{% /callout %}}


## Starting and restarting R Commander

### Start R Commander
To start R Commander type the `library(Rcmdr)` command behind the R Console prompt (indicated by a `>` sign) and press return (&#8617;) to execute the command.


### Restart R Commander
In case R Commander crashes while using it, you will need to resart it. However, in the R Console currently running R, the `library(Rcmdr)` command will not restart R Commander.

The reason is, that the R Commander package is still loaded and first needs to be detached. To detach the R Commander package you can copy (Ctrl+C) the following command:
```R
detach("package:Rcmdr", unload = TRUE)
```
paste (Ctrl+V) it behind the prompt in the R Console (indicated by a `>` sign) and press return (&#8617;) to execute the command.

Now R Commander can be restarted by using the `library(Rcmdr)` command as before.
