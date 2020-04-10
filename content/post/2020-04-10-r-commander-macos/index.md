---
title: "R Commander installation in R on macOS"
summary: "Instructions on how to install R Commander in R on macOS."
authors:
  - admin
date: '2020-04-10'
slug: r-commander-installation-in-r-on-macos
categories:
  - R
  - macOS
  - WUR
tags:
  - Installation
  - R Commander
  - R
  - macOS
lastmod: '2020-04-10T08:00:00+02:00'
draft: true
featured: false
image:
  caption: 'Image credit: [**_Daniel Romero_ on Unsplash**](https://unsplash.com/photos/4fy0sq4Iuow)'
  focal_point: 'Center'
  preview_only: false
projects: []
---

## Motivation
Due to the novel coronavirus (nCoV) and its related disease :mask: COVID-19 employees and students at Wageningen University & Research are all working from home. Students taking [Statistical Courses taught by Mathematical and Statistical Methods at Wageningen University & Research](https://www.wur.nl/en/Research-Results/Research-Institutes/plant-research/biometris/Education/BSc-and-Master-Courses.htm) will most likely use R. Students enrolled in [MAT-15303 Statistics 1](https://ssc.wur.nl/Handbook/Course/MAT-15303) and [MAT-15403 Statistics 2](https://ssc.wur.nl/Handbook/Course/MAT-15403) will use R Commander instead of basic R. Therefore, they will need to install R Commander.

{{% alert note %}}
This post will show how to install R Commander within R on a desktop or laptop computer running macOS as operating system.
{{% /alert %}}

In the text some symbol combinations are used for shortcuts, the following table explains the meaning of these symbols in relation to specific keys on your keyboard. To use the shortcuts press the keyboard keys simultaneously, e.g. &#8679;&#8984;A means &#8679;+&#8984;+A.

Icon    | Keyboard Meaning             | | Icon    | Keyboard Meaning              
--------|------------------------------|-|---------|-------------------------------
&#8984; | command                      | | &#8682; | caps lock                     
&#8997; | option (or alt)              | | &#8617; | carriage return (return/enter)
&#8963; | control                      | | &#9003; | delete/backspace              
fn      | function                     | | &#8998; | forward delete (fn + &#9003;) 
&#8679; | shift (either left or right) | | &#9099; | escape                        

## R Commander Installation
Prior requirements for the R Commander installation within R on macOS:

- [x] [R installed and configured on macOS](/post/2020/04/08/r-installation-macos/)
- [x] [XQuartz installed on macOS](/post/2020/04/09/xquartz-installation-macos/)

To be able to install R Commander you will need to have both R installed and configured as well as have XQuartz installed first. If you haven't done so already, please read the (re-)install and configure R on macOS as well as the XQuartz installation on macOS posts (use the links above to go to those specific posts) before continuing with this post.

To install R commander on macOS perform the following steps:

1. Start the R application from Finder > Applications (shortcut: &#8679;&#8984;A) or via Launchpad. The icon representing the R application is shown below.
![R application icon.](1-r-app-icon.png)
2. The R Console will open, as shown in the image below, and the cursor will be ready for input behind the prompt, as indicated by the `>` sign.
![R Console](4-r-app-console.png)



## AT THE END

Once the installation of the `RcmdrPlugin.HH` package has finised, you are ready :satisfied: to start R 3.6.3 and use R Commander.

{{% alert note %}}
**When using R Commander for the first time additional packages required for R Commander to work correctly will need to be installed. Allow the installation to be able to work smoothly without errors!**
{{% /alert %}}

To be added in following Posts:

- [x] [Install R on Windows 10](/post/2020/04/06/r-installation-windows-10/)
- [x] [Install R Commander in R on Windows 10](/post/2020/04/06/r-commander-installation-in-r-on-windows-10/)
- [x] [(re-)Install and Configure R on macOS](/post/2020/04/08/r-installation-macos/)
- [x] [Install XQuartz on macOS](/post/2020/04/09/xquartz-installation-macos)
- [ ] Install R Commander in R on macOS
- [ ] Install R Studio
