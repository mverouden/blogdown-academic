---
title: "R Commander installation in R on Windows 10/11"
subtitle: ''

# Summary for listings and search engines
summary: "Instructions on how to install R Commander in R on Windows 10/11."

# Link this post with a project
projects: []

# Date published
date: '2020-04-06'

# Date updated
lastmod: '2022-05-30T16:06:46+02:00'

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
  - Windows 10
  - Windows 11
  - WUR

tags:
  - Installation
  - R Commander
  - R
  - Windows 10
  - Windows 11

slug: r-commander-installation-in-r-on-windows-10

share: true
---

{{% toc %}}

## Motivation
<!--Due to the novel coronavirus (SARS-CoV-2) and its related disease :mask: COVID-19 employees and students at Wageningen University & Research are all working from home.-->

Whether working or studying everybody uses various sorts and types of software on their computer. Students taking [Statistical Courses, as taught by the Mathematical and Statistical Methods group at Wageningen University & Research](https://www.wur.nl/en/Research-Results/Research-Institutes/plant-research/biometris/Education/BSc-and-Master-Courses.htm), will most likely use R. Students enrolled in [MAT14303 Basic Statistics](https://wur.osiris-student.nl/#/onderwijscatalogus/extern/cursus?cursuscode=MAT14303&collegejaar=huidig), [MAT15303 Statistics 1](https://wur.osiris-student.nl/#/onderwijscatalogus/extern/cursus?cursuscode=MAT15303&collegejaar=huidig), [MAT15403 Statistics 2](https://wur.osiris-student.nl/#/onderwijscatalogus/extern/cursus?cursuscode=MAT154036&collegejaar=huidig) and [MAT20306 Advanced Statistics](https://wur.osiris-student.nl/#/onderwijscatalogus/extern/cursus?cursuscode=MAT20306&collegejaar=huidig) (first two weeks of this course) will use R Commander instead of basic R. Therefore, they will need to install R Commander.

{{% callout note %}}
This post will show how to install R Commander within R on a **privately owned** desktop or laptop computer running Windows 10/11 as operating system.
{{% /callout %}}

{{% callout warning %}}
The installation instructions in this post are <u>**not to be used on WURclient desktops or laptops**</u>! For a WURclient desktop or laptop see the post: [R Commander installation in R on a WURclient computer](/post/2021/04/23/r-commander-installation-in-r-on-wurclient/).
{{% /callout %}}

## R Commander Installation from the R GUI

{{% callout warning %}}
Students, who installed R by using the [WUR AppStore](/post/2020/04/06/r-installation-windows-10/#1-wur-appstore), can skip the installation of R Commander. The WUR AppStore version of R already contains everything to run R Commander.

This post is only intended for students, who followed the [Manual Installation](/post/2020/04/06/r-installation-windows-10/#2-manual-installation) of R.
{{% /callout %}}

Prior requirement:

- [x] [R installed on Windows 10/11](/post/2020/04/06/r-installation-windows-10/)

To be able to install R Commander you will need to have R installed first. If you haven't done so already, please first install R on your Windows 10/11 computer (use the link above to go to that specific post).

This post was originally based on R version 3.6.3. For newer versions of R the steps described are the same, only some screens you will see during your installation will display a higher version number of R compared to the screenshots in this post.

1. Start `R x64 4.3.3` from the ‘R’ folder in the ‘Start Menu’ as displayed below in [Figure 1](#figure-startmenu_r).

{{< figure src="r-commander-windows/startmenu-r.png" caption="Start Menu R x64" numbered="true" id="startmenu_r" >}}

2. The R GUI (graphical user interface) will open and the cursor will be ready for input behind the prompt, as indicated by the `>` sign. Use the mouse pointer and navigate to the top menu and select ‘Packages’ > ‘Install Package(s)...’ as shown in [Figure 2](#figure-install_packages_rgui).

{{< figure src="r-commander-windows/install-packages-r-gui.png" caption="R GUI Install Packages" numbered="true" id="install_packages_rgui" >}}

3. Now a CRAN (Comprehensive R Archive Network) mirror needs to be selected, from which packages will be installed. Select, as shown below in [Figure 3](#figure-select_cran_mirror), the top one ‘0-Cloud [https]’. This to make sure, that always the nearest CRAN mirror will be used no matter where you will be on the globe :earth_africa:. Click on the ‘OK’ button to confirm the selection.

{{< figure src="r-commander-windows/select-cran-mirror.png" caption="R GUI Select CRAN Mirror" numbered="true" id="select_cran_mirror" >}}

4. After the CRAN mirror selection a list of available packages will appear. Scroll down to find the `Rcmdr` package and click it to select. As shown below in [Figure 4](#figure-install_rcmdr_package) the package will turn blue, when selected. Confirm the installation by clicking the ‘OK’ button. Now a lot will happen in your display while the `Rcmdr` pacakage and its dependencies are being installed.

{{< figure src="r-commander-windows/install-package-Rcmdr.png" caption="R GUI Select the Rcmdr package to be installed." numbered="true" id="install_rcmdr_package" >}}

5. Repeat step 4. for installing the `RcmdrPlugin.HH` package. This plugin is required <!--in MAT-15403 Statistics 2--> to be able to do assignments about Simple Linear Regression.

{{% callout note %}}
Once the installation of the `RcmdrPlugin.HH` package has finished, you are ready :satisfied: to start R 4.3.3 and use R Commander.
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
