---
title: "Custom Anaconda installation on a WURclient computer"
subtitle: ''

# Summary for listings and search engines
summary: Instructions on how to install Anaconda yourself on a WURclient without using Software Center.

# Link this post with a project
projects: []

# Date published
date: '2022-11-03'

# Date updated
lastmod: '2022-11-04T12:00:00+02:00'

# Is this an unpublished draft?
draft: true

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
  - Anaconda
  - WURclient

categories:
  - Anaconda
  - WUR
  - WURclient

slug: anaconda-installation-wurclient

diagram: false

highlight: true

math: false

share: true
---

{{% toc %}}

## Motivation
A WURclient desktop or laptop at Wageningen University & Research is not a standard Windows 10 computer. WURclients use Windows 10 Enterprise, which has been modified by Facilities and Services Information Technology (FB-IT) among others with respect to installation rights for security reasons.

WURclient desktops and laptops at Wageningen University & Research can install Anaconda from the Software Center created by the IT department, which is launched by clicking on Start and selecting the "Software Center" tile. At the time this post was written the latest version of Anaconda in Software Center is `Anaconda Python 2021.11`.<!-- Currently the latest available version in Software Center is `Anaconda Python 2022.10`.-->

This version of Anaconda Python was packages for educational purposes. Only once per year a new version of Anaconda Python is released in Software Center and simultaneously in the WUR AppStore (course software for students).

Many users, however, would like to use a newer version of Anaconda Python than the one in Software Center. At the moment of writing this post the latest version of Anaconda Python released on [anaconda.com/products/distribution](https://www.anaconda.com/products/distribution) is Anaconda3 version 2022.10 containing Python 3.9.13 (released on 2022-10-17). <!--The post has been updated, with the exception of the screenshots, to R version 4.2.2 named: "Innocent and Trusting". -->

{{% callout note %}}
This post will show how to custom install Anaconda Python on a **WURclient** desktop or laptop computer without using Software Center.
{{% /callout %}}

{{% callout warning %}}
The installation instructions in this post are <u>**not to be used on privately owned desktops or laptops**</u>! For a privately owned desktop or laptop see the post: [Anaconda installation on Windows 10/11](/post/2020/04/06/r-installation-windows-10/).
{{% /callout %}}

## Prerequisite
To be able to perform a custom installation of R you need to have <u>**POWER USER RIGHTS**</u> on the WURclient desktop or laptop.

To see whether you possess these rights, right-click any icon (except Recycle Bin or WUR HELP) on the desktop. When the opened menu contains the option 'WUR - Run with administrative rights' (seventh or eighth from the top), it means you have power user rights on that particular desktop or laptop.

## Uninstall a previously installed Anaconda Python version
Before performing a new custom installation of Anaconda it is recommended to uninstall a previously installed version.

Here two procedures are described, follow the one that fits your needs:

* [Installed from Software Center](#installed-from-software-center)
* [Installed previously as a custom installation](#installed-previously-as-a-custom-installation)

In case you have no version of Anaconda installed on your WURclient desktop or laptop you can proceed to the section [Custom Anaconda installation](#custom-anaconda-installation).

### Installed from Software Center
If you previously installed Anaconda Python from Software Center, then to remove Anaconda Python reopen the Software Center by clicking on Start and next click on the Software Center tile. If for some reason you lack this tile in your start menu, just type 'Software Center' and it will appear in a search results window in your Windows task bar.

In the left column of Software Center navigate to "Installation Status". Select the installed Anaconda Python version and click on the green button bearing the text "Uninstall". This will start the removal of the software. You will be informed by the Software Center, when the software has been uninstalled.

{{% callout note %}}
If you have not installed another version of Anaconda Python, either via Software Center or via a custom installation, your computer should now be lacking a functioning Anaconda Python installation. Continue with the section [Custom Anaconda installation](#custom-anaconda-installation) to perform a new custom installation of Anaconda.

When you do still have a working Anaconda Python installation on your WURclient computer, return to [Uninstall a previously installed Anaconda version](#uninstall-a-previously-installed-anaconda-python-version) and follow the procedure applicable to your situation.
{{% /callout %}}

### Installed previously as a custom installation
Let's assume you previously installed Anaconda3 version 2021.11 on a WURclient computer (either a desktop or laptop) by following the steps for a custom installation of Anaconda as described in this post. For a newer version of Anaconda the steps are the same, but names of folders may differ.

To uninstall Anaconda perform the following steps:

1. Open a File Explorer and navigate to the folder `C:\MyPrograms\Anaconda3`. Right-click the file `Uninstall-Anaconda3.exe` and select 'WUR - Run with administrative rights' as displayed in [Figure 1](#figure-explorer_uninstall_anaconda) below.

{{< figure src="anaconda-wurclient/1-uninstall-anaconda.png" caption="Uninstall Custom Anaconda Installation from File Explorer." numbered="true" id="explorer_uninstall_anaconda" >}}

2. The uninstaller will start as shown below in [Figure 2](#figure-uninstall_anaconda). Click the 'Next >' to proceed.

{{< figure src="anaconda-wurclient/2-uninstaller-anaconda.png" caption="Welcome to Anaconda3 2021.11 (64-bit) Uninstall Announcement." numbered="true" id="uninstall_anaconda" >}}

3. The uninstaller proceeds to the next screen, as shown in [Figure 3](#figure-uninstall_anaconda_from), displaying the folder from where Anaconda3 will be uninstalled. Click the 'Uninstall' to proceed.

{{< figure src="anaconda-wurclient/3-uninstall-anaconda-from.png" caption="Uninstall Anaconda3 2021.11 (64-bit) from specified location." numbered="true" id="uninstall_anaconda_from" >}}

4. Once the uninstallation has completed, a message of success will be display as shown below in [Figure 4](#figure-uninstall_anaconda_success). Click the 'Next >' button to continue.

{{< figure src="anaconda-wurclient/4-successfull-uninstallation-anaconda.png" caption="Anconda Uninstallation Complete" numbered="true" id="uninstall_anaconda_success" >}}

5. To finish off the uninstallation click the 'Finish' button as displayed in [Figure 5](#figure-finish_uninstall_anaconda).

{{< figure src="anaconda-wurclient/5-finish-uninstall-anaconda.png" caption="Completing Anconda3 2021.11 (64-bit) Uninstall" numbered="true" id="finish_uninstall_anaconda" >}}

{{% callout note %}}
If you have not installed another version of Anaconda Python, either via Software Center or via a custom installation, your computer should now be lacking a functioning Anaconda Python installation. Continue with the section [Custom Anaconda installation](#custom-anaconda-installation) to perform a new custom installation of Anaconda.

When you do still have a working Anaconda Python installation on your WURclient computer, return to [Uninstall a previously installed Anaconda version](#uninstall-a-previously-installed-anaconda-python-version) and follow the procedure applicable to your situation.
{{% /callout %}}

## Custom Anaconda installation

To prepare the custom Anaconda installation a couple of folders need to be created prior to the installation of Anaconda. Perform the following steps exactly as described:

1. Search for the Command Prompt App by typing `cmd` in the search field of the Windows task bar.

2. The left part of the search results will show the Command Prompt App as best match and it will be highlighted in blue. Click on `Open file location` (third from the top) in the right part displaying the options for the Command Prompt App.

3. A File Explorer window will open with the shortcut to Command Prompt highlighted in blue. Right click the Command Prompt shortcut and select 'WUR - Run with adminstrative rights' as shown in [Figure 6](#figure-explorer_cmd_pusr3) below.

{{< figure src="r-wurclient/file_explorer_cmd.png" caption="Run CMD with 'WUR administrative rights' from File Explorer." numbered="true" id="explorer_cmd_pusr3" >}}

4. The Command Prompt application will open, as shown in [Figure 7](#figure-cmd_prompt3), on the folder `C:\Windows`. The top of the window shows that the Command Prompt application is used in Administrator mode (**<span style="color:red;">WARNING:</span> BE CAREFULL!!**).

{{< figure src="r-wurclient/cmd_with_admin_rights.png" caption="Command Prompt with Adminstrative Rights." numbered="true" id="cmd_prompt3" >}}

5. Create the directory `C:\MyPrograms`. In case the directory already exists, the message `A subdirectory or file C:\MyPrograms already exists.` will appear. To create the indicated folder copy (CTRL+C), paste (CTRL+V) the following line behind the prompt and press return (Enter) to execute it:
```sh
mkdir C:\MyPrograms
```

6. Next create the directory `C:\MyData`. This is done by copying (CTRL+C) the following line, pasting (CTRL+V) it behind the prompt and pressing return (Enter) to execute. In case the directory already exists, the message `A subdirectory or file C:\MyData already exists.` will appear.
```sh
mkdir C:\MyData
```

7. To close the Command Prompt application type `exit` and press return (Enter) to execute.

### Download
At the time this post was written, the latest release of Anaconda3 was version 2022.10.<!-- It has been updated to the latest release version 2022.10 of Anaconda3.-->

The installer for Windows 10/11 can be downloaded directly from this link: [{{< icon name="download" pack="fas" >}} Anaconda3 2022.10 for Windows (ca. 621.2MB, 64-bit).](https://repo.anaconda.com/archive/Anaconda3-2022.10-Windows-x86_64.exe)

{{% callout warning %}}
From Anaconda3 version 2022.10 the installer is only available for 64-bit Windows 10/11 and will not install on a 32-bit version of the Operating System.
{{% /callout %}}


### Installation
For newer versions of Anaconda3 than 2022.10 the steps described below are the same and still correct, but start with a newer version of the downloaded executable installer file of Anaconda3.<!-- The screenshots in this post have not been updated. Therefore, what you see during your installation will differ with respect to the version number shown in the screenshots.-->


1. Right-click the downloaded file **Anaconda3-2022.10-Windows-x86_64.exe** and select 'WUR - Run with administrative rights'. This file will most likely reside in your Downloads folder of your user account.
2. If asked for allow to install the software on your computer.
3. After the installer has started, a first selection window will appear as displayed below in [Figure 8](#figure-welcome_anaconda_setup). Click the ‘Next >’ button to proceed.

{{< figure src="anaconda-wurclient/6-welcome-installer-anaconda.png" caption="Welcome to Anaconda3 2022.11 (64-bit) Setup." numbered="true" id="welcome_anaconda_setup" >}}

4. The installer will now display the license agreement for installation of Anaconda3, as shown below in [Figure 9](#figure-agreement_anaconda_setup). Click on the ‘I Agree’ button to agree to the terms.

{{< figure src="anaconda-wurclient/7-license-agreement-anaconda.png" caption="Anaconda3 Setup License Agreement" numbered="true" id="agreement_anaconda_setup" >}}

5. After agreeing to the license terms, the Anaconda3 setup will ask for whom you wish to install for, as displayed in [Figure 10](#figure-install_for). Select the radio button ‘All Users (requires admin priveleges)’ and click on the ‘Next >’ button to proceed.

{{< figure src="anaconda-wurclient/8-selection-installation-type.png" caption="Anaconda3 Setup Select Installation Type" numbered="true" id="install_for" >}}

5. Having selected the installation type, the Anaconda3 setup will request for an installation location as shown in [Figure 11](#figure-install_location). Change the destination location to `C:\MyPrograms\Anaconda3`, to match [Figure 11](#figure-install_location), by typing the destination path directly into the text field displayed (currently showing `C:\ProgramData\Anaconda3`). Click on the ‘Next >’ button to continue.

{{< figure src="anaconda-wurclient/9-choose-install-location.png" caption="Anaconda3 Setup Choose Installation Location" numbered="true" id="install_location" >}}

6. After selecting the installation location folder the Advanced Installation Options will appear, as displayed below in [Figure 12](#figure-advanced_options). Leave the selection as displayed and click on the ‘Install’ button to start the installation.

{{< figure src="anaconda-wurclient/10-advanced-installation-options.png" caption="Anaconda3 Setup Advanced Installation Options" numbered="true" id="advanced_options" >}}

6. After selecting the components to install the startup options need to be set. Select, as shown in [Figure 13](#figure-install_r_customize_startup) below, the customized startup by selecting the ‘**Yes (customized startup)**’ radio button followed by clicking on the ‘Next’ button.

{{< figure src="r-wurclient/4-install-r-startup-options.png" caption="R Installation Customize Startup." numbered="true" id="install_r_customize_startup" >}}

7. The first startup option to set is the Display Mode, as shown in [Figure 14](#figure-install_r_display_mode). Select the Single Document Interface by selecting the ‘**SDI (separate windows)**’ radio button as displayed and clicking on the ‘Next’ button.

{{< figure src="r-wurclient/5-install-r-display-mode.png" caption="R Installation Display Mode Selection." numbered="true" id="install_r_display_mode" >}}

8. Next select the help style startup option. Leave this at the default ‘**HTML help**’ value, as displayed below in [Figure 15](#figure-install_r_help_style), and click on the ‘Next’ button.

{{< figure src="r-wurclient/6-install-r-help-style.png" caption="R Installation Help Style Selection." numbered="true" id="install_r_help_style" >}}

9. The one before last startup option is to set a ‘Start Menu’ folder name ([Figure 16](#figure-install_r_startmenu_folder)). Unless wishing to use a different name, leave the default value as displayed below. This will create a folder named ‘R’ in the ‘Start Menu’ of Windows, from which the R GUI (graphical user interface) can be started.

{{< figure src="r-wurclient/7-install-r-start-menu.png" caption="R Installation Start Menu Folder Selection." numbered="true" id="install_r_startmenu_folder" >}}

10. The last startup option to set allows for some customization of shortcut links. Preferably leave the default settings and continue by clicking on the ‘Next’ button. This will trigger the installation. At the end [Figure 17](#figure-install_r_success), shown below, will appear (although the version number will be different!). To exit the setup click on the ‘Finish’ button.

{{% callout warning %}}
**Do not mess around with the ‘Registry entries’  settings.**
{{% /callout %}}

{{< figure src="r-wurclient/9-install-r-completion.png" caption="R Installation Completed Successfully." numbered="true" id="install_r_success" >}}

11. To finalize the custom R installation on your WURclient desk- or laptop copy the files `Renviron.site` and `Rprofile.site` from the Downloads folder on your computer and paste them into the `C:\MyPrograms\R\R-4.2.2\etc`. A window will appear, as displayed below in [Figure 18](#figure-replace_file), to indicate, that the file `Rprofile.site` already exists. Select 'Replace the file in the destination'.

{{< figure src="r-wurclient/replace_rprofile_site_file.png" caption="Replace Rprofile.site File." numbered="true" id="replace_file" >}}

{{% callout note %}}
Congratulations, :satisfied:, you now have R version 4.2.2 installed on your WURclient desktop or laptop computer!
{{% /callout %}}

### Changing the R startup working directory

In this custom installation procedure the R HOME directory is set to `C:\MyData`. This means, that at the start the default working directory in R is set to `C:\MyData`. You change this by changing the HOME environment variable in the file `Renviron.site`. The file resides in the `C:\MyPrograms\R\R-4.2.2\etc` directory.

To change the R HOME environment variable perform the following steps:

1. Open a File Explorer and navigate to the `C:\MyPrograms\R\R-4.2.2\etc` folder

2. Right-click the file `Renviron.site` and select the **`Open with`** option. Windows will prompt you to select an application to open the `Renviron.site` file with, as shown below in [Figure 19](#figure-open_with).

{{< figure src="r-wurclient/renviron_site_open_with.png" caption="Open Renviron.site with." numbered="true" id="open_with" >}}

3. First remove the check mark in front of 'Always use this app to open .site files'. Select either Notepad or Wordpad to modify the `Renviron.site` file. When neither is offered, click on the blue text 'More apps' to select either Notepad or Wordpad.

4. Once an editor has been chosen, the file will open in the chosen editor. The first two lines of the 'Renviron.site` file read:
```sh
## Set the user's home directory
HOME='C:/MyData/'
```

5. Modify `'C:/MyData/'` to the preferred startup working directory for R. For example `'M:/My Documents/MyR'` would set the default R working directory to the 'My Documents\MyR' folder of your WUR M:-drive, provided that the folder 'MyR' exists as a sub folder of 'M:\My Documents'. Do not forget to save the file (CRTL+S) to make the change permanent.
