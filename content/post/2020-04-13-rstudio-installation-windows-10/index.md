---
## The title of your page (Core)
title: "RStudio installation on Windows 10/11"
## An optional subtitle that will be displayed under the title
subtitle: ''

## Add the short URL slug containing keywords
slug: 'rstudio-installation-on-windows-10'

## A one-sentence summary of the content on your page. 
##   The summary can be shown on the homepage and can also benefit your search
##   engine ranking.
summary: "Instructions on how to install RStudio on Windows 10/11."

## Display the authors of the page and link to their user profiles if they exist.
authors:
  - admin

## Tagging your content helps users to discover similar content on your site. 
##   Tags can improve search relevancy and are displayed after the page content
##   and also in the Tag Cloud widget.
tags:
  - Installation
  - RStudio
  - R
  - Windows 10
  - Windows 11

## Categorizing your content helps users to discover similar site content.
##   Categories can improve search relevancy and display at the top of a page
##   alongside a page’s metadata.
categories:
  - R
  - Windows 10
  - Windows 11
  - WUR

## The RFC 3339 date that the page was published. 
date: '2020-04-13'
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
lastmod: '2024-05-03T07:22:10+02:00'

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
  # placement: 2
  caption: 'Image credit: [**_Panos Sakalakis_ on Unsplash**](https://unsplash.com/photos/AwDVMJKMjlU)'
  focal_point: "Center"
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
#     url: 'https://twitter.com/mverouden'
#   # - icon_pack: fab
#   #   icon: medium
#   #   name: Originally published on Medium
#   #   url: 'https://medium.com'   # (required)

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
math: false

## Enable a Markdown extension for diagrams by toggling the diagram 
##   option in your `config/_default/params.yaml` file or by adding
##   `diagram: true` to your page front matter.
diagram: false

## Image gallery:
## To add an image gallery to a page bundle
# Discarded for any remote gallery images see: https://wowchemy.com/blog/v5.1.0/#apply-breaking-changes
# gallery_item:
#   - album: 'branch-bundle-1'
#     image: 'GW150914Anniversary.png'
#     caption: 'Write your image caption here'  # only shown when zoom out
#     order: "asc" # "asc" or "desc"
#     resize_options:  # which supports Hugo image processing options.
#   # - album: gallery        # can not be replaced
#   #   image: 'sketch5.png'  # `static/media/sketch5.png`
#   #   caption: A caption    # only shown when zoom out
#   # - album: gallery
#   #   image: https://vip1.loli.net/2020/11/11/OmVGhaz79iQJsvj.png
#   #   caption: Another caption  # only shown when zoom out

## (Optional) Header image (relative to `assets/media/` folder).
##   To display a full width header image, the header parameters below can be 
##   inserted towards the end of a page’s front matter. It is assumed that the 
##   image is located in your `assets/media/` media library
# header:
#   image: "header.png"
#   caption: "Image credit: [**MLflow**](https://mlflow.org)"
---

{{% toc %}}

## Motivation
<!--Due to the novel coronavirus (SARS-CoV-2) and its related disease :mask: COVID-19 employees and students at Wageningen University & Research are all working from home.-->

Whether working or studying everybody uses various sorts and types of software on their computer. Students taking [Statistical Courses, as taught by the Mathematical and Statistical Methods group at Wageningen University & Research](https://www.wur.nl/en/Research-Results/Research-Institutes/plant-research/biometris/Education/BSc-and-Master-Courses.htm), will most likely use R.

Some of these courses (e.g. [MAT-20306](https://ssc.wur.nl/Handbook/Course/MAT-20306), [MAT-32806](https://ssc.wur.nl/Handbook/Course/MAT-32806), and [MAT-50303](https://ssc.wur.nl/Handbook/Course/MAT-50303)) mainly use RStudio. Also other courses (e.g. [HNH-31506](https://ssc.wur.nl/Handbook/Course/HNH-31506) and [BIF-51306](https://ssc.wur.nl/Handbook/2019/Course/BIF51306)) taught at Wageningen University & Research use R through RStudio as well. Therefore, students will need to be able to install RStudio.

{{% callout note %}}
This post will show how to install RStudio on a **privately owned** desktop or laptop computer running Windows 10/11 as operating system.
{{% /callout %}}

{{% callout warning %}}
The installation instructions in this post are <u>**not to be used on WURclient desktops or laptops**</u>! For a WURclient desktop or laptop see the post: [Custom RStudio installation on a WURclient computer](/post/2021/06/17/rstudio-installation-wurclient/).
{{% /callout %}}

Two ways to install R are offered here:

1. [WUR AppStore](#1-wur-appstore). This is the **RECOMMENDED** way!
2. [Manual installation](#2-manual-installation) for those who, for whatever reason, do not want to use the WUR AppStore.

## 1. WUR AppStore
The WUR AppStore is the place where you will be able to download, link to, or virtually access the software you need for your study program and courses. Not only during, but also for self-study after, the computer practical's and courses. 

Prior requirement for the installation of RStudio via the WUR AppStore:

- [x] [R installed on Windows 10/11 via the WUR AppStore](/post/2020/04/06/r-installation-windows-10/#1-wur-appstore)

The WUR AppStore currently contains RStudio version 2024.04.2 Build 764 under the name **RStudio 2024.04.2764**.

## 2. Manual Installation

### Download
At the time this post was written, the latest stable release of RStudio was version 1.2.5033. The post has been updated to the current stable release version 2025.05.0 Build 496 (named "Mariposa Orchid").

Download RStudio using the following link: [{{< icon name="download" pack="fas" >}} RStudio 2025.05.0 Build 496 (ca. 281.27 MB)](https://download1.rstudio.org/electron/windows/RStudio-2025.05.0-496.exe)

For newer versions of RStudio the steps described after the download are the same, but starting with a newer version of the RStudio executable file.

### RStudio Installation
Prior requirement for the installation of RStudio:

- [x] [R installed on Windows 10/11 via Manual Installation](/post/2020/04/06/r-installation-windows-10/#2-manual-installation)

To be able to install RStudio you will need to have R installed first. If you haven't done so already, please first install R on your Windows 10/11 computer (use the link above to go to that specific post).

To install RStudio on Windows 10/11 perform the following steps:

1. Open the downloaded file **RStudio-2025.05.0-496.exe**. This file will most likely reside in the Downloads folder of your user account.
2. Allow to install the software on your computer.
3. After the installler has started, a Welcome window will appear as displayed below in [Figure 1](#figure-rstudio_setup). Click the ‘Next’ button to proceed.

{{< figure src="rstudio-windows/1-rstudio-w10.png" caption="Welcome screen RStudio Setup." numbered="true" id="rstudio_setup" >}}

4. Now the RStudio Setup will allow you to select the installation location by selecting a destination folder, as shown in [Figure 2](#figure-rstudio_install_location) below. Leave the default specified folder or, if you know what you are doing, select an alternative installation destination folder, then click the ‘Next’ button to continue. 

{{< figure src="rstudio-windows/2-rstudio-location-w10.png" caption="RStudio Installation Location Selection." numbered="true" id="rstudio_install_location" >}}

5. Next the RStudio Setup allows choosing a Start Menu folder, as displayed below in [Figure 3](#figure-rstudio_startmenu_folder), where the RStudio shortcut to start the program will be put. Click on ‘Install’ to start the installation of RStudio.

{{< figure src="rstudio-windows/3-rstudio-start-folder-w10.png" caption="Setting the RStudio Start Menu Folder." numbered="true" id="rstudio_startmenu_folder" >}}

6. Once the installation of RStudio has finished, the window will look like the one shown below in [Figure 4](#figure-rstudio_install_completed). Click the ‘Finish’ button to close the setup.

{{< figure src="rstudio-windows/5-rstudio-completed-w10.png" caption="RStudio Installation Completion." numbered="true" id="rstudio_install_completed" >}}

{{% callout note %}}
Congratulations, :satisfied:, you now have RStudio 2025.05.0 Build 496 installed on your private Windows desktop or laptop computer!
{{% /callout %}}
