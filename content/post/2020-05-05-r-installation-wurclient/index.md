---
title: Custom R installation on a WURclient computer
summary: Instructions on how to install R yourself on a WURclient without using !Available Software.
authors:
- admin
date: '2020-05-05'
slug: r-installation-wurclient
categories:
  - R
  - WUR
tags:
  - Installation
  - R
  - WURclient
lastmod: '2020-05-05T23:59:00+02:00'
draft: true
featured: false
image:
  caption: 'Image credit: [**_Panos Sakalakis_ on Unsplash**](https://unsplash.com/photos/AwDVMJKMjlU)'
  focal_point: 'Center'
  preview_only: false
projects: []
---

{{% toc %}}

## Motivation
WURclient desktops and laptops at Wageningen University & Research can install R from the Sofware Center created by the IT department, which is launched by clicking on Start and selecting the !Avalable Software tile. At the time this post was written the latest version of R in !Available Software/Software Center is `R 3.6.1 Rcmdr`.

This version of R was developed for educational purposes, where `Rcmdr` reflects that the installer includes R Commander. Only once per year a new version of R (including R Commander and additional packages for serveral courses) is released in !Available Software. The consequence is, that core packages can not be updated by users.

Many users, however, need to be able to update core packages, because of dependencies with packages they would like to install or would just like to use a newer version of R than the one in !Available Software. At the moment of writing this post the latest version of R released on [r-project.org](https://www.r-project.org/) is R version 4.0.0 named: "Arbor Day" (released on 2020-04-24).

{{% callout note %}}
This post will show how to custom install R on a **WURclient** desktop or laptop computer without using !Available Software.
{{% /callout %}}

{{% callout warning %}}
The installation instructions in this post are <u>**not to be used on privately owned desktops or laptops**</u>! For a privately owned desktop or laptop see the post: [R installation on Windows 10](/post/2020/04/06/r-installation-windows-10/).
{{% /callout %}}

## Prerequisite
To be able to perform a custom installation of R you need to have <u>**POWER USER RIGHTS**</u> on the WURclient desktop or laptop.

To see whether you posses these rights, right-click any icon (except Recycle Bin or WUR HELP) on the desktop. When the opened menu contains the option "WUR - Run with administative rights" (sixth from the top), it means you have power user rights on that particular desktop or laptop.

## Uninstall a previously installed version
Before performing a new custom installation of R it is recommended to uninstall a previously installed version.

### Installed from !Available Software
If you previously installed R from !Available Software/Software Center, then to remove R reopen the Software Center by clicking on Start and next click on the !Available Software tile. If for some reason you lack this tile in your start menu, just type !Available Software and it will appear in your search bar.

In the left column of Sofware Center navigate to "Installation Status". Select the installed R version and click on the green button bearing the text "Uninstall". This will start the removal of the software. You will be informed by the Software Center, when the uninstallation of the software has completed.

Next you will need to remove the packages, you have installed manually.

{{% callout warning %}}
Be aware that all packages you have installed manually will be removed, if you continue here!
{{% /callout%}}

Let's asume you had previously installed `R 3.6.1 Rcmdr` from !Available Software/Sofware Center. The user installed packages will reside in `C:/ProgramData/R/win-library/3.6`. If you try to remove the folder via File Explorer in Windows, you will discover that you have insufficient rights to do so. The reason is that !Available Software/Software Center installs software with **ADMINISTRATOR RIGHTS**, you on the other hand only have **POWER USER RIGHTS**. The **POWER USER** does not have full administrator privileges!

However, there is a way to still delete the previously manually installed packages from `C:/ProgramData/R/win-library/3.6`. To do so you need to use either Command Prompt or Windows PowerShell with **POWER USER RIGHTS**. 

### Installed previously as a Custom Installation
If you followed this post before to do a Custom Installation of R on a WURclient computer (either a desk- or a lap-top)

## Download
At the time this post was written the latest release of R is version 3.6.3. The installer for Windows 10 can be downloaded directly from this link: [R 3.6.3 for Windows (c. 83 MB, 32- & 64-bit)](https://cloud.r-project.org/bin/windows/base/old/3.6.3/R-3.6.3-win.exe).

## Installation

1. Open the downloaded file **R-3.6.3-win.exe**. This file will most likely reside in your Downloads folder of your user account.
2. Allow to install the software on your computer.
3. After the installler has started, a first selection window will appear as displayed below. Select the English language and click the ‘OK’ button to proceed.

![Language selection during R installation.](1-install-r-language.png)

4. Click on the ‘Next’ button to agree the terms. After  this a window will appear, allowing you to select or choose the destination folder, as shown below, where R 3.6.3 for Windows should be installed. If you are content with the default `C:\Program Files\R\R-3.6.3` click on the ‘Next’ button to continu, otherwise use the ‘B<u>r</u>owse...’ button to navigate to an alternative destination or type the destination path directly into the text field displayed (currently showing `C:\Program Files\R\R-3.6.3`).

![Destination folder during R installation.](2-install-r-destination-folder.png)

5. After selecting the installation destination folder the component selector will appear, as displayed below. Most desktop and laptop computers these days are using a 64-bit architecture, therefore select (using the pull down menu) the 64-bit User installation as displayed in the image shown below and click on the ‘Next’ button.

![Component selection during R installation.](3-install-r-select-components.png)

6. After selecting the components to install the startup options need to be set. Select, as shown below, the customized startup by selecting the ‘Yes’ radiobutton followed by clicking on the ‘Next’ button.

![Customized startup selection during R installation.](4-install-r-startup-options.png)

7. The first startup options to set is the Display Mode, as show below. Select the Single Document Interface by selecting the ‘SDI (separate windows)’ radiobutton as displayed and clicking on the ‘Next’ button.

![Display mode selection during R installation.](5-install-r-display-mode.png)

8. Next select the help style startup option. Leave this at the default ‘HTML help’ value, as displayed below, and click on the ‘Next’ button.

![Help style selection during R installation.](6-install-r-help-style.png)

9. The one before last startup setting is to set a ‘Start Menu’ folder name. Unless wishing to use a different name, leave the default value as displayed below. This will create a folder named ‘R’ in the ‘Start Menu’ of Windows, from which the R GUI (graphical user interface) can be started.

![Start menu folder selection during R installation.](7-install-r-start-menu.png)

10. The last startup setting to set allows for some customization of shortcut links. Preferably leave the default settings and continue by clicking on the ‘Next’ button. This will trigger the installation. At the end the image shown below will appear. To exit the setup click on the ‘Finish’ button.

{{% callout warning %}}
**Do not mess around with the ‘Registry entries’  settings.**
{{% /callout %}}

![Completion of the R installation.](9-install-r-completion.png)

{{% callout note %}}
Congratulations, :satisfied:, you now have R 3.6.3 installed on your private desktop or laptop computer!
{{% /callout %}}
