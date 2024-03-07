---
title: "R Commander installation in R on macOS"
subtitle: ''

# Summary for listings and search engines
summary: "Instructions on how to install R Commander in R on macOS."

# Link this post with a project
projects: []

# Date published
date: '2020-04-10'

# Date updated
lastmod: '2022-05-30T19:15:30+02:00'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: [**_Maxim Hopman_ on Unsplash**](https://unsplash.com/photos/Hin-rzhOdWs)'
  focal_point: 'Center'
  # placement: 2
  preview_only: false

authors:
  - admin

tags:
  - Installation
  - R Commander
  - R
  - macOS

categories:
  - R
  - macOS
  - WUR

slug: r-commander-installation-in-r-on-macos

share: true
---

{{% toc %}}

## Motivation
<!--Due to the novel coronavirus (SARS-CoV-2) and its related disease :mask: COVID-19 employees and students at Wageningen University & Research are all working from home.-->

Whether working or studying everybody uses various sorts and types of software on their computer. Students taking [Statistical Courses, as taught by the Mathematical and Statistical Methods group at Wageningen University & Research](https://www.wur.nl/en/Research-Results/Research-Institutes/plant-research/biometris/Education/BSc-and-Master-Courses.htm), will most likely use R. Students enrolled in [MAT-14303 Basic Statistics](https://ssc.wur.nl/Handbook/Course/MAT-14303), [MAT-15303 Statistics 1](https://ssc.wur.nl/Handbook/Course/MAT-15303), [MAT-15403 Statistics 2](https://ssc.wur.nl/Handbook/Course/MAT-15403) and [MAT-20306 Advanced Statistics](https://ssc.wur.nl/Handbook/Course/MAT-20306) (first two weeks of this course) will use R Commander instead of basic R. Therefore, they will need to install R Commander.

{{% callout note %}}
This post will show how to install R Commander within R on a desktop or laptop computer running macOS as operating system.
{{% /callout %}}

In the text some symbol combinations are used for shortcuts, the following table explains the meaning of these symbols in relation to specific keys on your keyboard. To use the shortcuts press the keyboard keys simultaneously, e.g. &#8679;&#8984;A means &#8679;+&#8984;+A.

|  Icon   | &nbsp; | Keyboard Meaning             | &nbsp;&nbsp; |  Icon   | &nbsp; | Keyboard Meaning               |
|:-------:|:------:|:-----------------------------|:------------:|:-------:|:------:|:-------------------------------|
| &#8984; | &nbsp; | command                      | &nbsp;&nbsp; | &#8682; | &nbsp; | caps lock                      |
| &#8997; | &nbsp; | option (or alt)              | &nbsp;&nbsp; | &#8617; | &nbsp; | carriage return (return/enter) |
| &#8963; | &nbsp; | control                      | &nbsp;&nbsp; | &#9003; | &nbsp; | delete/backspace               |
| fn      | &nbsp; | function                     | &nbsp;&nbsp; | &#8998; | &nbsp; | forward delete (fn + &#9003;)  |
| &#8679; | &nbsp; | shift (either left or right) | &nbsp;&nbsp; | &#9099; | &nbsp; | escape                         |

## R Commander Installation
Prior requirements for the R Commander installation within R on macOS:

- [x] [R installed and configured on macOS](/post/2020/04/08/r-installation-macos/)
- [x] [XQuartz installed on macOS](/post/2020/04/09/xquartz-installation-macos/)

To be able to install R Commander you will need to have both R installed and configured as well as have XQuartz installed first. If you haven't done so already, please read the (re-)install and configure R on macOS as well as the XQuartz installation on macOS posts (use the links above to go to those specific posts) before continuing with this post.

The screenshots in this post are based on R version 3.6.3. However, the procedure and steps described are still correct for higher versions of R.

To install R commander on macOS perform the following steps:

1. Start the R application from Finder > Applications (shortcut: &#8679;&#8984;A) or via Launchpad. The icon representing the R application is shown in [Figure 1](#figure-r_app_icon) below.

{{< figure src="r-commander-macos/1-r-app-icon.png" caption="Icon R Application" numbered="true" id="r_app_icon" >}}

2. The R Console will open, as shown below in [Figure 2](#figure-r_app_console), and the cursor will be ready for input behind the prompt, as indicated by the `>` sign.

{{< figure src="r-commander-macos/4-r-app-console.png" caption="R Application Console" numbered="true" id="r_app_console" >}}

3. In case the ‘command line developer tools’ requirement window appears as shown in [Figure 3](#figure-otool_install) below, click ‘Cancel’ to make it disappear. **There is no need to install it!**

{{< figure src="r-commander-macos/2-r-app-otool-install.png" caption="Developer Tools Requirement" numbered="true" id="otool_install" >}}

4. Navigate the mouse pointer to the menu bar click on ‘Packages & Data’ and select the ‘Package Installer’ (shortcut: &#8997;&#8984;I). This will cause the R Package Installer to open as shown below in [Figure 4](#figure-r_package_install).

{{< figure src="r-commander-macos/5-r-app-package-installer-rcmdr.png" caption="R Package Installer for Rcmdr" numbered="true" id="r_package_install" >}}

5. First click on the ‘Get List’ to retrieve the available packages on the CRAN mirror. Next type `Rcmdr` in the ‘Package Search’ field and press return (&#8617;) to execute the search. Select the `Rcmdr` package in the results list underneath by clicking on it, which will make it turn blue to indicate the selection. In the last block named ‘Install Location’ select the radio button ‘At User Level’ and tick the checkbox ‘Install Dependencies’. When the ‘Package Installer’ window matches the one shown in [Figure 4](#figure-r_package_install) above, you click the ‘Install Selected’ button.
6. Loads of packages will be downloaded and installed. When the installation has finished, the ‘Package Installer’ will resemble the image shown below in [Figure 5](#figure-r_package_rcmdrplugin).

{{< figure src="r-commander-macos/6-r-app-package-installer-plugin.hh.png" caption="R Package Installer for RcmdrPlugin.HH" numbered="true" id="r_package_rcmdrplugin" >}}

7. Now select the `RcmdrPlugin.HH`. Make sure your ‘Install Location’ is still set to ‘At User Level’ and that the checkbox ‘Install Dependencies’ is still ticked, before clicking the ‘Install Selected’ button.

Once the installation of the `RcmdrPlugin.HH` package has finised, you are ready to use R Commander for the first time :satisfied:. 

{{% callout warning%}}
**Continue with the next section "First time use of R Commander" now. Do not wait until the first Computer Practicum!**
{{% /callout %}}

## First time use of R Commander

{{% callout note %}}
**When using R Commander for the first time additional packages required for R Commander to work correctly will need to be installed. Allow the installation to be able to work smoothly without errors!**
{{% /callout %}}

To start R Commander from the R Console, type the command `library(Rcmdr)` behind the prompt, as indicated by the `>` sign, and and press return (&#8617;) to execute. This will cause R Commander to be started.

{{% callout warning%}}
When starting __R Commander__ via `Packages & Data` > `Packages Manager` in the top bar menu of __R__ and marking the tick box in front of the `Rcmdr` package, many users experience that R Commander fails to show the menu items in the top bar menu of R Commander. This is resolved by starting R Commander by explicitly type the command `library(Rcmdr)` at the prompt and executing by pressing return (&#8617;) instead of using the graphical user interface of R to load the `Rcmdr` package.
{{% /callout %}}

The first time you start R Commander, you will see at the bottom of the main R Commander window in the ‘Messages’ section the message as shown in [Figure 6](#figure-rcmdr_app_nap) below.

{{< figure src="r-commander-macos/7-r-commander-app-nap-warning.png" caption="R Commander App Nap Warning" numbered="true" id="rcmdr_app_nap" >}}

The warning is referring to a feature that was added to macOS in 2013, which  is called App Nap. App Nap puts programs you are not currently actively using or looking at into ‘sleep’ mode, blocking them from using system resources, especially the CPU, until you focus on them again. It will cause R Commander to work not very smoothly, because the R application is being put to ‘sleep’ as it is running in the background of R Commander. R Commander will at moments work with a huge lag time, which will feel like it is frozen and not responding.

**Solving this problem will ask quite a bit of your patience! Fortunately you only have to do this once, afterwards R Commander will work smoothly every time you start it.** 

Perform the following steps:

1. Navigate the mouse pointer to the top menu of the R Commander window and click on ‘Tools’. Patiently wait until the menu unfolds as shown below in [Figure 7](#figure-rcmdr_tools_menu). **Only click once and wait patiently!**

{{< figure src="r-commander-macos/8-r-commander-manange-app-nap.png" caption="R Commander Tools Menu Item." numbered="true" id="rcmdr_tools_menu" >}}

2. Next move the mouse pointer to the menu item ‘Manage Mac OS X app nap for R.app...’ and click on it. **Again only click once and wait patiently!** This will open the ‘Mac OS X app nap for R.app’ window to open as shown below in [Figure 8](#figure-rcmdr_app_nap_off).

{{< figure src="r-commander-macos/9-r-commander-app-nap-off.png" caption="Mac OS X app nap for R.app Window." numbered="true" id="rcmdr_app_nap_off" >}}

3. Select the radio button ‘off (recommended)’. Wait for the selection to change. After the change occurs, click on ‘OK’ to confirm.
4. Navigate the mouse pointer to the top menu of the R Commander window and click on ‘File’. Wait patiently for the menu item to unfold. Navigate to ‘Exit’ > ‘From Commander’ and click only once it. Wait for the ‘Exit?’ window to appear and click ‘OK’. This closes R Commander.
5. Click on the R Console window to make it the active application.
6. Quit the R application either by:
    * Typing `q()` or `quit()` behind the R Console prompt (indicated by the `>` sign) and pressing return (&#8617;) to execute.
    * Using the keyboard shortcut: &#8984;Q
    * Navigating the mouse pointer to the menu bar and clicking ‘R’ > ‘Quit R’
    * Navigation the mouse pointer to the top left corner of the R Console window and clicking on the red ball
6. No matter what you choose, you will always be asked whether you want to save a workspace image as shown below in [Figure 9](#figure-r_save_workspace). Just click on the **‘Don't Save’** button to end the R application.

{{< figure src="r-commander-macos/10-r-app-save-workspace.png" caption="R Application Save Workspace." numbered="true" id="r_save_workspace" >}}

{{% callout note %}}
Next time you start R Commander from the R Console of the R application using the `library(Rcmdr)` command, the ‘Messages’ section will display the following or a similar message: `[1] NOTE: R Commander Version 2.9-2:` followed by the day, date and time. Now R Commander will work smoothly.
{{% /callout %}}

## Alternative way of starting R Commander without the App nap problem
As an alternative to switching off the App Nap for the R application you could start R from a Terminal.

This is done by following these steps:

1. Open the Terminal application from Finder > Applications > Utilities (shorcut: &#8679;&#8984;U) or via Lauchpad under the ‘Other’ group. The terminal console prompt, where the commands will be entered, is depicted by a `%` or a `$` sign. Which sign is shown, depends whether your default shell is zsh (`%` sign) or bash (`$` sign).
2. Type `R` behind the prompt in the terminal console and press return (&#8617;) to execute the command.
3. This will start R and the prompt, where the commands will be entered for R, will have changed into a `>` sign.
4. Type the command `library(Rcmdr)` behind the prompt, as indicated by the `>` sign, and and press return (&#8617;) to execute. This will cause R Commander to be started. The ‘Messages’ section at the bottom of R Commander will display the following or a similar message: `[1] NOTE: R Commander Version 2.9-1:` followed by the day, date and time. This means that R Commander will work smoothly!

Quitting R Commander will return you to the terminal console, which can be recognized by the prompt sign changing back into a `%` or `$` sign.

To quit the active terminal console by typing `exit` and pressing return (&#8617;) to execute. To quit the Terminal application completely you can use the keyboard shortcut: &#8984;Q or navigate the mouse pointer to the menu bar and click ‘Terminal’ > ‘Quit Terminal’.

## Restarting R Commander
In case R Commander crashes while using it, you will need to resart it. However, in the R Console or in the active terminal console currently running R, the `library(Rcmdr)` command will not restart R Commander.

The reason is, that the R Commander package is still loaded and first needs to be detached. To detach the R Commander package you can copy (&#8984;C) the following command:
```R
detach("package:Rcmdr", unload = TRUE)
```
paste (&#8984;V) it behind the prompt in the R console (indicated by a `>` sign) and press return (&#8617;) to execute the command.

Now R Commander can be restarted by using the `library(Rcmdr)` command as before. 
