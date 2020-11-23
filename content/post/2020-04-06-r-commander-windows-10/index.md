---
title: "R Commander installation in R on Windows 10"
summary: "Instructions on how to install R Commander in R on Windows 10."
authors:
  - admin
date: '2020-04-06'
slug: r-commander-installation-in-r-on-windows-10
categories:
  - R
  - Windows 10
  - WUR
tags:
  - Installation
  - R Commander
  - R
  - Windows 10
lastmod: '2020-04-06T16:11:35+02:00'
draft: false
featured: false
image:
  caption: 'Image credit: [**_Panos Sakalakis_ on Unsplash**](https://unsplash.com/photos/AwDVMJKMjlU)'
focal_point: 'Center'
preview_only: false
projects: []
---

{{% toc %}}

## Motivation
Due to the novel coronavirus (SARS-CoV-2) and its related disease :mask: COVID-19 employees and students at Wageningen University & Research are all working from home. Students taking [Statistical Courses taught by Mathematical and Statistical Methods at Wageningen University & Research](https://www.wur.nl/en/Research-Results/Research-Institutes/plant-research/biometris/Education/BSc-and-Master-Courses.htm) will most likely use R. Students enrolled in [MAT-15303 Statistics 1](https://ssc.wur.nl/Handbook/Course/MAT-15303) and [MAT-15403 Statistics 2](https://ssc.wur.nl/Handbook/Course/MAT-15403) will use R Commander instead of basic R. Therefore, they will need to install R Commander.

{{% callout note %}}
This post will show how to install R Commander within R on a **privately owned** desktop or laptop computer running Windows 10 as operating system.
{{% /callout %}}

{{% callout warning %}}
The installation instructions in this post are <u>**not to be used on WURclient desktops or laptops**</u>!
{{% /callout %}}

## R Commander Installation
Prior requirement:

- [x] [R installed on Windows 10](/post/2020/04/06/r-installation-windows-10/)

To be able to install R Commander you will need to have R installed first. If you haven't done so already, please first install R on your Windows 10 computer (use the link above to go to that specific post).

Two installation methods will be described here:

- Using the `library.zip` file downloaded from Brightspace.
- Manual installation from the R GUI (graphical user interface)

The first method using the `library.zip` file is recommended. However, if due to issues with Administrative Rights this does not work, try the manual installation from the R GUI.

This post was originally based on R version 3.6.3. For newer versions of R the steps desribed are the same, only some screens you will see during your installation will display a higher version number of R compared to the screenshots in this post.

### Installation using the `library.zip` file from Brightspace.
 
1. Download the `library.zip` file in Brightspace from either the course MAT-15303 Statistics 1 or MAT-15403 Statistics 2. This file can be found on the respective course page under ‘Content’ > ‘Practicals’ > ‘library (Zip Compressed File)’. Behind the text you see a downwards mark. Click on this and select ‘Download’. This will download the `library.zip` file into your Downloads folder of your user account. Below you see the downloaded file in the Windows File Explorer.

![Downloaded `library.zip file in Windows File Explorer`](1-rcmdr-install-library.png)

2. Right-click the `library.zip` file and select ‘Extract All...’ as shown in the image below.

![Extract all from `library.zip`](2-rcmdr-install-extract-all-library.png)

3. A new window will open, where you have to set the destination for the extracted folders and files. Click ‘B<u>r</u>owse...’ and select the following destination: `C:\Program Files\R\R-4.0.2\library` as shown below, but for version 3.6.3.

![Destination for extracted folders and files.](3-rcmdr-install-extract-all-destination.png)

4. If a message pops-up, check the box ‘Do this for <u>a</u>ll current items’ and click on the ‘<u>C</u>ontinue’ button.

The extraction process can take 10 to 15 minutes before all folders and files are extracted to the specified location. When the extraction process has finished, you are ready :satisfied: to start R 4.0.2 and use R Commander.


### Manual installation from the R GUI

1. Start `R x64 4.0.2` from the ‘R’ folder in the ‘Start Menu’ as displayed below.

![Start Menu R x64](startmenu-r.png)

2. The R GUI (graphical user interface) will open and the cursor will be ready for input behind the prompt, as indicated by the `>` sign. Use the mouse pointer and navigate to the top menu and select ‘Packages’ > ‘Install Package(s)...’ as shown below.

![R GUI prompt](install-packages-r-gui.png)

3. Now a CRAN (Comprehensive R Archive Network) mirror needs to be selected, from which packages will be installed. Select, as shown below, the top one ‘0-Cloud [https]’. This to make sure, that always the nearest CRAN mirror will be used no matter where you will be on the globe :earth_africa:. Click on the ‘OK’ button to confirm the selection.

![Select CRAN mirror.](select-cran-mirror.png)

4. After the CRAN mirror selection a list of available packages will appear. Scroll down to find the `Rcmdr` package and click it to select. As shown below the package will turn blue, when selected. Confirm the installation by clicking the ‘OK’ button. Now a lot will happen in your display while the `Rcmdr` pacakage and its dependencies are being installed.

![Select the Rcmdr package to be installed.](install-package-Rcmdr.png)

5. Repeat step 4. for installing the `RcmdrPlugin.HH` package. This plugin is required for MAT-15403 Statistics 2 to be able to do the practicals on Simple Linear Regression.

{{% callout note %}}
Once the installation of the `RcmdrPlugin.HH` package has finised, you are ready :satisfied: to start R 4.0.2 and use R Commander.
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
