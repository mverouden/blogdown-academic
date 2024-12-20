---
title: "RStudio installation on macOS"
subtitle: ''

# Summary for listings and search engines
summary: "Instructions on how to install RStudio on macOS."

# Link this post with a project
projects: []

# Date published
date: '2020-04-13'

# Date updated
lastmod: '2022-05-30T19:19:19+02:00'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: [**_Maxim Hopman_ on Unsplash**](https://unsplash.com/photos/Hin-rzhOdWs)'
  focal_point: 'Center'
  #placement: 2
  preview_only: false

authors:
  - admin

tags:
  - Installation
  - RStudio
  - R
  - macOS

categories:
  - R
  - macOS
  - WUR

slug: rstudio-installation-on-macos

share: true
---

{{% toc %}}

## Motivation
<!--Due to the novel coronavirus (SARS-CoV-2) and its related disease :mask: COVID-19 employees and students at Wageningen University & Research are all working from home.-->

Whether working or studying everybody uses various sorts and types of software on their computer. Students taking [Statistical Courses, as taught by the Mathematical and Statistical Methods group at Wageningen University & Research](https://www.wur.nl/en/Research-Results/Research-Institutes/plant-research/biometris/Education/BSc-and-Master-Courses.htm), will most likely use R.

Some of these courses (e.g. [MAT-20306](https://ssc.wur.nl/Handbook/Course/MAT-20306), [MAT-32806](https://ssc.wur.nl/Handbook/Course/MAT-32806), and [MAT-50303](https://ssc.wur.nl/Handbook/Course/MAT-50303)) mainly use RStudio. Also other courses (e.g. [HNH-31506](https://ssc.wur.nl/Handbook/Course/HNH-31506) and [BIF-51306](https://ssc.wur.nl/Handbook/2019/Course/BIF51306)) taught at Wageningen University & Research use R through RStudio as well. Therefore, students will need to be able to install RStudio.

{{% callout note %}}
This post will show how to install RStudio on a desktop or laptop computer running macOS as operating system.
{{% /callout %}}

In the text some symbol combinations are used for shortcuts, the following table explains the meaning of these symbols in relation to specific keys on your keyboard. To use the shortcuts press the keyboard keys simultaneously, e.g. &#8679;&#8984;A means &#8679;+&#8984;+A.

|  Icon   | &nbsp; | Keyboard Meaning             | &nbsp;&nbsp; |  Icon   | &nbsp; | Keyboard Meaning               |
|:-------:|:------:|:-----------------------------|:------------:|:-------:|:------:|:-------------------------------|
| &#8984; | &nbsp; | command                      | &nbsp;&nbsp; | &#8682; | &nbsp; | caps lock                      |
| &#8997; | &nbsp; | option (or alt)              | &nbsp;&nbsp; | &#8617; | &nbsp; | carriage return (return/enter) |
| &#8963; | &nbsp; | control                      | &nbsp;&nbsp; | &#9003; | &nbsp; | delete/backspace               |
| fn      | &nbsp; | function                     | &nbsp;&nbsp; | &#8998; | &nbsp; | forward delete (fn + &#9003;)  |
| &#8679; | &nbsp; | shift (either left or right) | &nbsp;&nbsp; | &#9099; | &nbsp; | escape                         |

## Download
At the time this post was written the latest stable release of RStudio was version 1.2.5033. It has been updated to the current stable release 2024.12.0 Build 467 (nicknamed "Kousa Dogwood"), which will work on macOS Ventura (version 13.x) or later.

Download RStudio using the following link: [{{< icon name="download" pack="fas" >}} RStudio 2024.12.0 Build 467 (ca. 617.71 MB)](https://download1.rstudio.org/electron/macos/RStudio-2024.12.0-467.dmg)

If you are on a 32 bit system, you can use an [older version of RStudio](https://docs.posit.co/previous-versions/rstudio/).

## RStudio Installation
The screenshots in the installation steps described below have not been updated. However, the procedure is correct even for newer versions of RStudio. Just bear in mind, that what you see during your installation may differ from the screenshots shown. 

Prior requirement for the RStudio installation on macOS:

- [x] [R installed and configured on macOS](/post/2020/04/08/r-installation-macos/)

To be able to install RStudio you will need to have R installed and configured first. If you haven't done so already, please read the (re-)install and configure R on macOS (use the link above to go to that specific post) before continuing with this post.

To install RStudio on macOS perform the following steps:

1. Open the downloaded RStudio disk image. This file will most likely reside in Finder > Downloads (shortcut: &#8997;&#8984;L). The file can more easily be found by switching into List view (shortcut: &#8984;2). To switch to Icon view use the shortcut: &#8984;1. The Rstudio disk image will look like the image displayed below in [Figure 1](#figure-rstudio_disk_image) (version number may or will differ).

{{< figure src="rstudio-macos/1-rstudio-dmg-icon.png" caption="Icon RStudio Disk Image Application" numbered="true" id="rstudio_disk_image" >}}

2. Opening the RStudio disk image will cause a window labeled ‘RStudio-xxxx.xx.x-xxx’ to appear (xxxx.xx.x-xxx represents the version number used), containing the RStudio application (see [Figure 2](#figure-rstudio_install)).

{{< figure src="rstudio-macos/2-rstudio-install.png" caption="RStudio Application Inside Disk Image" numbered="true" id="rstudio_install" >}}

3. Drag the RStudio application and drop it on the Applications folder shown in the same window.
4. Close the ‘RStudio-xxxx.xx.x-xxx’ window by clicking on the red ball in the top left corner of the window.
5. The opened disk image is still mounted as a volume on your desktop and will look like the image shown below in [Figure 3](#figure-rstudio_mounted). Click this icon on your desktop once to select it and press &#8984;E (shortcut for eject) to close it. Now you can discard the downloaded `RStudio-xxxx.xx.x-xxx.dmg` file from Finder > Downloads (shortcut: &#8997;&#8984;L) by clicking it once to select and using the shortcut &#8998; (press: fn + &#9003;) to put it in the trashbin. To completely remove the installer disk image remove it from your trashbin.

{{< figure src="rstudio-macos/3-rstudio-desktop-volume.png" caption="Mounted RStudio Volume" numbered="true" id="rstudio_mounted" >}}

{{% callout note %}}
Congratulations, :satisfied:, you now have successfully installed RStudio on your mac! The icon in your Applications (shortcut: &#8679;&#8984;A) or Launcher will look the same as the R application icon you dragged and dropped in step 3. of the installation steps described above.
{{% /callout %}}
