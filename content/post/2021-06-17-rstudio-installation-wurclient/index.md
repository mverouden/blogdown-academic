---
title: "Custom RStudio installation on a WURclient computer"
subtitle: ''

# Summary for listings and search engines
summary: "Instructions on how to install RStudio yourself on a WURclient without using Software Center."

# Link this post with a project
projects: []

# Date published
date: '2021-06-17'

# Date updated
lastmod: '2022-05-30T22:01:00+02:00'

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

tags:
  - Installation
  - R
  - RStudio
  - WURclient

categories:
  - R
  - WUR
  - WURclient

slug: rstudio-installation-wurclient

diagram: false

highlight: true

math: false

share: true
---

{{% toc %}}

## Motivation
A WURclient desktop or laptop at Wageningen University & Research is not a standard Windows 10 computer. WURclients use Windows 10 Enterprise, which has been modified by Facilities and Services Information Technology (FB-IT) among others with respect to installation rights for security reasons.

WURclient desktops and laptops at Wageningen University & Research can install RStudio from the Software Center, before called !Available Software, created by the IT department, which is launched by clicking on Start and selecting the 'Software Center' tile. At the time this post was written, the latest version of RStudio in Software Center was `RStudio v1.4`, which refers to release `v1.4.1717`. Currently `RStudio 2023.06.1.524` is the latest available version in Software Center, referring to release `2023.06.1 Build 524`.

This version of RStudio was placed in 'Software Center' for educational purposes. Only once per year a new version of R (including R Commander and additional packages for several courses) and RStudio is released in Software Center.

Many users, however, prefer to use the latest version of RStudio, because of new features offered in the newer version of the software. At the moment of writing this post the latest version of RStudio was v1.4.1717 named: 'Juliet Rose' (released on 2021-06-01). The post has been updated, with the exception of the screenshots, to `RStudio 2023.06.2 Build 561` named: "Mountain Hydrangea".

{{% callout note %}}
This post will show how to custom install RStudio on a **WURclient** desktop or laptop computer without using Software Center.
{{% /callout %}}

{{% callout warning %}}
The installation instructions in this post are <u>**not to be used on privately owned desktops or laptops**</u>! For a privately owned desktop or laptop see the post: [RStudio installation on Windows 10](/post/2020/04/13/rstudio-installation-on-windows-10/).
{{% /callout %}}

### Prerequisites

- [x] To be able to perform a custom installation of RStudio you need to have <u>**POWER USER RIGHTS**</u> on the WURclient desktop or laptop.

To see whether you possess these rights, right-click any icon (except Recycle Bin or WUR HELP) on the desktop. When the opened menu contains the option 'WUR - Run with administrative rights' (sixth or seventh from the top), it means you have power user rights on that particular desktop or laptop.

- [x] [R installed on a WURclient using a custom installation ](/post/2021/01/24/r-installation-wurclient/)

To be able to install RStudio you will need to have R installed first. If you haven't done so already, please first perform a custom installation of R on your WURclient computer (use the link above to go to that specific post).

## Uninstall a previously installed RStudio version
Before performing a new custom installation of RStudio it is recommended to uninstall a previously installed version.

Here two procedures are described, follow the one that fits your needs:

* [Installed from Software Center](#installed-from-software-center)
* [Installed previously as a custom installation](#installed-previously-as-a-custom-installation)

In case you have no version of RStudio installed on your WURclient desktop or laptop you can proceed to the section [Custom RStudio installation](#custom-rstudio-installation).

### Installed from Software Center
If you previously installed RStudio from Software Center, then to remove R reopen the Software Center by clicking on Start and next click on the Software Center tile. If for some reason you lack this tile in your start menu, just type 'Software Center' and it will appear in a search results window in your Windows task bar.

In the left column of Software Center navigate to 'Installation Status'. Select the installed RStudio version and click on the green button bearing the text 'Uninstall'. This will start the removal of the software. You will be informed by the Software Center, when the software has been uninstalled.

{{% callout note %}}
If you have not installed another version of RStudio, either via Software Center or via a custom installation, your computer should now be lacking a functioning RStudio installation. Continue with the section [Custom RStudio installation](#custom-rstudio-installation) to perform a new custom installation of RStudio.

When you do still have a working RStudio installation on your WURclient computer, return to [Uninstall a previously installed RStudio version](#uninstall-a-previously-installed-rstudio-version) and follow the procedure applicable to your situation.
{{% /callout %}}

### Installed previously as a custom installation
Let's assume you previously installed RStudio version 1.3.959 on a WURclient computer (either a desktop or laptop) by following the steps for a custom installation of RStudio as described in this post. For a newer version of RStudio the steps are the same.<!--, but names of folders will differ with respect to the R version number.-->

To uninstall RStudio perform the following steps:

1. Open a File Explorer and navigate to the folder `C:\MyPrograms\RStudio`. Right-click the file `Uninstall.exe` and select 'WUR - Run with administrative rights' as displayed in [Figure 1](#figure-explorer_uninstall_rstudio) below.

{{< figure src="rstudio-wurclient/uninstall_custom_rstudio_installation.png" caption="Uninstall Custom RStudio Installation from File Explorer." numbered="true" id="explorer_uninstall_rstudio" >}}

2. The uninstaller will start as shown below in [Figure 2](#figure-uninstall_rstudio). Click the 'Uninstall' to proceed.

{{< figure src="rstudio-wurclient/rstudio_uninstaller.png" caption="RStudio for Windows Uninstall Announcement." numbered="true" id="uninstall_rstudio" >}}

3. Once the uninstallation has completed, a message of success will be display as shown below in [Figure 3](#figure-uninstall_rstudio_success). Click the 'Close' button to finish.

{{< figure src="rstudio-wurclient/rstudio_uninstall_completed.png" caption="RStudio for Windows Uninstalled Successfully." numbered="true" id="uninstall_rstudio_success" >}}

{{% callout note %}}
If you have not installed another version of RStudio, either via Software Center or via a custom installation, your computer should now be lacking a functioning RStudio installation. Continue with the section [Custom RStudio installation](#custom-rstudio-installation) to perform a new custom installation of RStudio.

When you do still have a working RStudio installation on your WURclient computer, return to [Uninstall a previously installed RStudio version](#uninstall-a-previously-installed-rstudio-version) and follow the procedure applicable to your situation.
{{% /callout %}}

## Custom RStudio installation

### Download
At the time this post was written, the latest stable release of RStudio was version 1.4.1717. The post has been updated to the current stable release 2023.06.2 Build 561.

Download RStudio using the following link: [{{< icon name="download" pack="fas" >}} RStudio 2023.06.2 Build 561 (ca. 212.78 MB)](https://download1.rstudio.org/electron/windows/RStudio-2023.06.2-561.exe)

For newer versions of RStudio the steps described after the download are the same, but starting with a newer version of the RStudio executable file.

### Installation
To install RStudio perform the following steps:

1. Right-click the downloaded file **RStudio-2023.06.2-561.exe** and select 'WUR - Run with administrative rights'. This file will most likely reside in your Downloads folder of your user account.
2. After the installler has started, a Welcome window will appear as displayed below in [Figure 4](#figure-rstudio_setup). Click the ‘Next’ button to proceed.

{{< figure src="rstudio-windows/1-rstudio-w10.png" caption="Welcome screen RStudio Setup." numbered="true" id="rstudio_setup" >}}

3. Now the RStudio Setup will allow you to select the installation location by selecting a destination folder. Change the Destination Folder to `C:\MyPrograms\Rstudio`, , as shown in [Figure 5](#figure-rstudio_install_location) below. Click the ‘Next’ button to continue. 

{{< figure src="rstudio-wurclient/rstudio_installation_folder.png" caption="RStudio Installation Location Selection." numbered="true" id="rstudio_install_location" >}}

4. Next the RStudio Setup allows choosing a Start Menu folder, as displayed below in [Figure 6](#figure-rstudio_startmenu_folder), where the RStudio shortcut to start the program will be put. Click on ‘Install’ to start the installation of RStudio.

{{< figure src="rstudio-windows/3-rstudio-start-folder-w10.png" caption="Setting the RStudio Start Menu Folder." numbered="true" id="rstudio_startmenu_folder" >}}

5. Once the installation of RStudio has finished, the window will look like the one shown below in [Figure 7](#figure-rstudio_install_completed). Click the ‘Finish’ button to close the setup.

{{< figure src="rstudio-windows/5-rstudio-completed-w10.png" caption="RStudio Installation Completion." numbered="true" id="rstudio_install_completed" >}}

{{% callout note %}}
Congratulations, :satisfied:, you now have RStudio 2023.06.2 Build 561 installed on your WURclient desk- or laptop computer!
{{% /callout %}}

## Setting the default RStudio working directory

In the default R GUI the working directory at start up is:
```r
\\\\WURNET.NL/Homes/user001/My Documents
```
where user001 display your own WUR username, as described in the section [Changing the R GUI working directory](/post/2021/01/24/r-installation-wurclient/#changing-the-r-gui-working-directory) of the post [Custom R installation on a WURclient computer](/post/2021/01/24/r-installation-wurclient).

In RStudio the default working directory of the R Console and Files tab can be set in the **Global Options...** item under **Tools** in the top menu:

1. a new window will open by default in the _**General**_ part,

2. go to **R Sessions** and select your "Default working directory (when not in a project):" by setting the desired folder using the **Browse** button.

When restarting RStudio you will notice, that both the R console and the Files tab open in the selected default working directory.

<!-- ## Warning Message RStudio

Lately I have been getting many e-mails claiming that R/RStudio, from Software Center or the custom installation, is not working well within Wageningen University & Research.

Usually the mail contains the following console message:
```r
Warning message:
In normalizePath(path.expand(path), winslash, mustWork) :
  path[1]="//WURNET.NL/Homes/user001/My Documents": Access is denied
```
, where `user001` displays the user's own personal WUR username.

It is merely a **WARNING MESSAGE**.

This message is only given in RStudio, because it is a persistent problem originating from the use of RStudio within a network environment. On the Fora of RStudio this problem has been appearing since 2014 and has still not been resolved by RStudio.

Whether you installed R and RStudio on a WURclient using Software Center or via the posts of this website, the warning message does not hamper the working of R in RStudio.

As user you can check, where packages are installed using the following command in RStudio:
```r
.libPaths()
```
For a custom installation R will return in the console:
```r
[1] "C:/ProgramData/R/win-library/4.2" "C:/MyPrograms/R/R-4.2.0/library"
```
In case you have a custom installation and the returned paths are different, it means you didn't follow the steps for the installation of R as described. Please reinstall R as described in [R installed on a WURclient using a custom installation ](/post/2021/01/24/r-installation-wurclient/).


The installation via Software Center will return in the console:
```
[1] "C:/ProgramData/R/win-library/4.1" "C:/Program Filess/R/R-4.1.0/library"
```
In case you have installed via Software Center, but get different paths I urgently request you to contact first the Servicedesk IT. When they can not solve the issue, I will be contacted via them. -->
