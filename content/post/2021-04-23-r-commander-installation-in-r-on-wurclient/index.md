---
title: "R Commander installation in R on a WURclient computer"
subtitle: ''

# Summary for listings and search engines
summary: "Instructions on how to install R Commander in R on a WURclient computer."

# Link this post with a project
projects: []

# Date published
date: '2021-04-23'

# Date updated
lastmod: '2022-05-30T21:27:00+02:00'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: [**_Panos Sakalakis_ on Unsplash**](https://unsplash.com/photos/AwDVMJKMjlU)'
  focal_point: 'Center'
    # placement: 2
  preview_only: false

authors:
- admin

categories:
  - R
  - WUR
  - WURclient

tags:
  - Installation
  - R Commander
  - R
  - WURclient

slug: r-commander-installation-in-r-on-wurclient

diagram: false

highlight: true

math: false

share: true
---

{{% toc %}}

## Motivation
A WURclient desktop or laptop at Wageningen University & Research is not a standard Windows 10 computer. WURclients use Windows 10 Enterprise, which has been modified by Facilities and Services Information Technology (FB-IT) among others with respect to installation rights for security reasons.

WURclient desktops and laptops at Wageningen University & Research can install R from the Software Center created by the IT department, which is launched by clicking on Start and selecting the "Software Center" tile. At the time this post was written the latest version of R in Software Center is `R 4.1.0 Rcmdr`. Currently the latest available version in Software Center is `R 4.3.1 Rcmdr`.

This version of R was packaged for educational purposes, where `Rcmdr` reflects that the installer includes R Commander. Only once per year a new version of R (including R Commander and additional packages for serveral courses) is released in Software Center. The consequence is, that core packages can not be updated by users.

Many users, however, need to be able to update core packages, because of dependencies with packages they would like to install or would just like to use a newer version of R than the one in Software Center. At the moment of writing this post the latest version of R released on [r-project.org](https://www.r-project.org/) is R version 4.0.5 named: "Shake and Throw" (released on 2021-03-31). The post has been updated to R version 4.3.1 named: "Beagle Scouts".

Some users will also like to install the latest version of R Commander on their WURclient, after having installed the latest version of R via a custom installation without using Software Center. 

{{% callout note %}}
This post will show how to install R Commander within R on a **WURclient** desktop or laptop computer after a custom R installation.
{{% /callout %}}

{{% callout warning %}}
The installation instructions in this post are <u>**not to be used on privately owned desktops or laptops**</u>! For a privately owned desktop or laptop see the post: [R Commander installation in R on Windows 10](/post/2020/04/06/r-commander-installation-in-r-on-windows-10/).
{{% /callout %}}

## R Commander Installation from the R GUI
Prior requirement:

- [x] [R installed on a WURclient using a custom installation](/post/2021/01/24/r-installation-wurclient/)

To be able to install R Commander you will need to have R installed first. If you haven't done so already, please first perform a custom installation of R on your WURclient computer (use the link above to go to that specific post).

Some Figures in this post are based on R version 3.6.3. For newer versions of R the steps described are the same, only some screens you will see during your installation will display a higher version number of R compared to the screenshots in the figures of this post.

1. Start `R x64 4.3.1` from the ‘R’ folder in the ‘Start Menu’ as displayed below in [Figure 1](#figure-startmenu_r).

{{< figure src="r-commander-windows/startmenu-r.png" caption="Start Menu R x64" numbered="true" id="startmenu_r" >}}

2. The R GUI (graphical user interface) will open and the cursor will be ready for input behind the prompt, as indicated by the `>` sign. Use the mouse pointer and navigate to the top menu and select ‘Packages’ > ‘Install Package(s)...’ as shown in [Figure 2](#figure-install_packages_rgui).

{{< figure src="r-commander-windows/install-packages-r-gui.png" caption="R GUI Install Packages" numbered="true" id="install_packages_rgui" >}}

3. Now a CRAN (Comprehensive R Archive Network) mirror needs to be selected, from which packages will be installed. Select, as shown below in [Figure 3](#figure-select_cran_mirror), the top one ‘0-Cloud [https]’. This to make sure, that always the nearest CRAN mirror will be used no matter where you will be on the globe :earth_africa:. Click on the ‘OK’ button to confirm the selection.

{{< figure src="r-commander-windows/select-cran-mirror.png" caption="R GUI Select CRAN Mirror" numbered="true" id="select_cran_mirror" >}}

4. After the CRAN mirror selection a list of available packages will appear. Scroll down to find the `Rcmdr` package and click it to select. As shown below in [Figure 4](#figure-install_rcmdr_package) the package will turn blue, when selected. Confirm the installation by clicking the ‘OK’ button. Now a lot will happen in your display while the `Rcmdr` pacakage and its dependencies are being installed.

{{< figure src="r-commander-windows/install-package-Rcmdr.png" caption="R GUI Select the Rcmdr package to be installed." numbered="true" id="install_rcmdr_package" >}}

5. Repeat step 4. for installing the `RcmdrPlugin.HH` package or any other additional Plugin for R Commander you need. The `HH` plugin for example provides additional functionality for Simple Linear Regression.

{{% callout note %}}
Once the installation of the `RcmdrPlugin.HH` package, or any other additional Plugins you require, has finished, you are ready :satisfied: to start R version 4.3.1 and use R Commander.
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
