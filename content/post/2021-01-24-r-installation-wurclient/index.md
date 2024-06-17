---
title: "Custom R installation on a WURclient computer"
subtitle: ''

# Summary for listings and search engines
summary: Instructions on how to install R yourself on a WURclient without using Software Center.

# Link this post with a project
projects: []

# Date published
date: '2021-01-24'

# Date updated
lastmod: '2022-05-30T21:17:00+02:00'

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
  - WURclient

categories:
  - R
  - WUR
  - WURclient

slug: r-installation-wurclient

diagram: false

highlight: true

math: false

share: true
---

{{% toc %}}

## Motivation
A WURclient desktop or laptop at Wageningen University & Research is not a standard Windows 10 computer. WURclients use Windows 10 Enterprise, which has been modified by Facilities and Services Information Technology (FB-IT) among others with respect to installation rights for security reasons.

WURclient desktops and laptops at Wageningen University & Research can install R from the Software Center created by the IT department, which is launched by clicking on Start and selecting the "Software Center" tile. <!--At the time this post was written the latest version of R in Software Center is `R 4.1.0 Rcmdr`. -->Currently the latest available version in Software Center is `R 4.3.3 Rcmdr`.

This version of R was packaged for educational purposes, where `Rcmdr` reflects that the installer includes R Commander. Only once per year a new version of R (including R Commander and additional packages for serveral courses) is released in Software Center. Users can update all packages in this release, even the core packages in the so-called **_System Library_**. The pre-installed packages in the **_User Library_** can be uninstalled, when not needed.

Many users, however, would just like to use a newer version of R than the one in Software Center. When this post was written the release version of R on [r-project.org](https://www.r-project.org/) was 4.0.3, named: "Bunny-Wunnies Freak Out" (released on 2020-10-10). The post has been updated, with the exception of the screenshots, to latest R version 4.4.1, named: "Race for Your Life" (released on 2024-06-14).

{{% callout note %}}
This post will show how to custom install R on a **WURclient** desktop or laptop computer without using Software Center.
{{% /callout %}}

{{% callout warning %}}
The installation instructions in this post are <u>**not to be used on privately owned desktops or laptops**</u>! For a privately owned desktop or laptop see the post: [R installation on Windows 10/11](/post/2020/04/06/r-installation-windows-10/).
{{% /callout %}}

## Prerequisite
- [x] To be able to perform a custom installation of R you need to have <u>**POWER USER RIGHTS**</u> on the WURclient desktop or laptop.

To see whether you possess these rights, right-click any icon (except Recycle Bin or WUR HELP) on the desktop. When the opened menu contains the option 'WUR - Run with administrative rights' (seventh or eighth from the top), it means you have power user rights on that particular desktop or laptop.

## Uninstall a previously installed R version
Before performing a new custom installation of R it is recommended to uninstall a previously installed version.

Here two procedures are described, follow the one that fits your needs:

* [Installed from Software Center](#installed-from-software-center)
* [Installed previously as a custom installation](#installed-previously-as-a-custom-installation)

In case you have no version of R installed on your WURclient desktop or laptop you can proceed to the section [Custom R installation](#custom-r-installation).

### Installed from Software Center
If you previously installed R from Software Center, then to remove R reopen the Software Center by clicking on Start and next click on the Software Center tile. If for some reason you lack this tile in your start menu, just type 'Software Center' and it will appear in a search results window in your Windows task bar.

In the left column of Software Center navigate to "Installation Status". Select the installed R version and click on the green button bearing the text "Uninstall". This will start the removal of the software. You will be informed by the Software Center, when the software has been uninstalled.

Next you will need to remove the packages, you have installed manually (added yourself via the `install.packages()` command in R).

{{% callout warning %}}
Be aware that all packages you have installed manually will be removed, if you continue here!
{{% /callout%}}

Let's assume you had previously installed `CRAN R 3.6.1 Rcmdr` from Software Center on your WURclient computer. The user installed packages will reside in `C:\ProgramData\R\win-library\3.6`. If you try to remove the folder via File Explorer in Windows, you will discover that you have insufficient rights to do so. The reason is that Software Center installs software with **ADMINISTRATOR RIGHTS**, you on the other hand only have **POWER USER RIGHTS**. The **POWER USER** does not have full administrator privileges!

However, there is a way to still delete the previously manually installed packages from `C:\ProgramData\R\win-library\3.6`. To do so you need to use either Command Prompt or Windows PowerShell with **POWER USER RIGHTS**. Perform the following steps:

1. Search for the Command Prompt application by typing `cmd` in the search field (displayed as a magnifying glass) of the Windows task bar.

2. The left part of the search results will show the Command Prompt App as best match and it will be highlighted in blue. Click on `Open file location` (third from the top) in the right part displaying the options for the Command Prompt App.

3. A File Explorer window will open with the shortcut to Command Prompt highlighted in blue. Right-click the Command Prompt shortcut and select 'WUR - Run with adminstrative rights' as shown in [Figure 1](#figure-explorer_cmd_pusr) below.

{{< figure src="r-wurclient/file_explorer_cmd.png" caption="Run CMD with 'WUR administrative rights' from File Explorer." numbered="true" id="explorer_cmd_pusr" >}}

4. The Command Prompt application will open, as shown in [Figure 2](#figure-cmd_prompt) below, on the folder `C:\Windows`. The top of the window shows that the Command Prompt application is used in Administrator mode (**<span style="color:red;">WARNING:</span> BE CAREFULL!!**).

{{< figure src="r-wurclient/cmd_with_admin_rights.png" caption="Command Prompt with Adminstrative Rights." numbered="true" id="cmd_prompt" >}}

5. Change the working directory to `C:\ProgramData`. This is done by copying (CTRL+C) the following line, pasting (CTRL+V) it behind the prompt and pressing return (Enter) to execute.
```sh
cd C:\ProgramData
```

6. Remove the directory `C:\ProgramData\R\win-library\3.6` with all its content (subdirectories and files). This is done by copying (CTRL+C) the following line, pasting (CTRL+V) it behind the prompt and pressing return (Enter) to execute.
```sh
rmdir /S C:\ProgramData\R\win-library\3.6
```

7. The question `C:\ProgramData\R\win-library\3.6, Are you sure (Y/N)?` will appear. Confirm the removal of the directory with all its content by answering `Y`.

8. The Command Prompt application can now be closed by typing `exit` and executing it by pressing return (Enter).

{{% callout note %}}
If you have not installed another version of R, either via Software Center or via a custom installation, your computer should now be lacking a functioning R installation. Continue with the section [Custom R installation](#custom-r-installation) to perform a new custom installation of R.

When you do still have a working R installation on your WURclient computer, return to [Uninstall a previously installed R version](#uninstall-a-previously-installed-r-version) and follow the procedure applicable to your situation.
{{% /callout %}}

### Installed previously as a custom installation
Let's assume you previously installed R version 3.6.3 on a WURclient computer (either a desktop or laptop) by following the steps for a custom installation of R as described in this post. For a newer version of R the steps are the same, but names of folders will differ with respect to the R version number.

To uninstall R and delete the manually installed packages (added yourself via the `install.packages()` command in R) perform the following steps:

1. Open a File Explorer and navigate to the folder `C:\MyPrograms\R\R-3.6.3`. Right-click the file `unins000.exe` and select 'WUR - Run with administrative rights' as displayed in [Figure 3](#figure-explorer_uninstall_r) below.

{{< figure src="r-wurclient/uninstall_custom_r_installation.png" caption="Uninstall Custom R Installation from File Explorer." numbered="true" id="explorer_uninstall_r" >}}

2. The uninstaller will start as shown below in [Figure 4](#figure-uninstall_r). Click the 'Yes' to proceed.

{{< figure src="r-wurclient/r_v3.6.3_uninstall.png" caption="R for Windows Uninstall Announcement." numbered="true" id="uninstall_r" >}}

3. Once the uninstallation has completed, a message of success will be display as shown below in [Figure 5](#figure-uninstall_r_success). Click the 'OK' button to finish.

{{< figure src="r-wurclient/successfull_uninstallation_r.png" caption="R for Windows Uninstalled Successfully." numbered="true" id="uninstall_r_success" >}}

4. Search for the Command Prompt application by typing `cmd` in the search field (displayed as a magnifying glass) of the Windows task bar.

5. The left part of the search results will show the Command Prompt App as best match and it will be highlighted in blue. Click on `Open file location` (third from the top) in the right part displaying the options for the Command Prompt App.

6. A File Explorer window will open with the shortcut to Command Prompt highlighted in blue. Right-click the Command Prompt shortcut and select 'WUR - Run with adminstrative rights' as shown in [Figure 6](#figure-explorer_cmd_pusr2) below.

{{< figure src="r-wurclient/file_explorer_cmd.png" caption="Run CMD with 'WUR administrative rights' from File Explorer." numbered="true" id="explorer_cmd_pusr2" >}}

7. The Command Prompt application will open, as shown in [Figure 7](#figure-cmd_prompt2) below, on the folder `C:\Windows`. The top of the window shows that the Command Prompt application is used in Administrator mode (**<span style="color:red;">WARNING:</span> BE CAREFULL!!**).

{{< figure src="r-wurclient/cmd_with_admin_rights.png" caption="Command Prompt with Adminstrative Rights." numbered="true" id="cmd_prompt2" >}}

8. Change the working directory to `C:\MyPrograms`. This is done by copying (CTRL+C) the following line, pasting (CTRL+V) it behind the prompt and pressing return (Enter) to execute.
```sh
cd C:\MyPrograms
```

9. Remove the directory `C:\MyPrograms\R\R-3.6.3` with all its content (subdirectories and files). This is done by copying (CTRL+C) the following line, pasting (CTRL+V) it behind the prompt and pressing return (Enter) to execute.
```sh
rmdir /S R\R-3.6.3
```

10. The question `R\R-3.6.3, Are you sure (Y/N)?` will appear. Confirm the removal of the directory with all its content by answering `Y`.

11. To delete the manually installed packages (added yourself via the `install.packages()` command in R) change the working directory to `C:\ProgramData`. This is done by copying (CTRL+C) the following line, pasting (CTRL+V) it behind the prompt and pressing return (Enter) to execute.
```sh
cd C:\ProgramData
```

12. Remove the directory `C:\ProgramData\R\win-library\3.6` with all its content (subdirectories and files). This is done by copying (CTRL+C) the following line, pasting (CTRL+V) it behind the prompt and pressing return (Enter) to execute.
```sh
rmdir /S C:\ProgramData\R\win-library\3.6
```

13. The question `C:\ProgramData\R\win-library\3.6, Are you sure (Y/N)?` will appear. Confirm the removal of the directory with all its content by answering `Y`.

14. The Command Prompt application can now be closed by typing `exit` and executing it by pressing return (Enter).

{{% callout note %}}
If you have not installed another version of R, either via Software Center or via a custom installation, your computer should now be lacking a functioning R installation. Continue with the section [Custom R installation](#custom-r-installation) to perform a new custom installation of R.

When you do still have a working R installation on your WURclient computer, return to [Uninstall a previously installed R version](#uninstall-a-previously-installed-r-version) and follow the procedure applicable to your situation.
{{% /callout %}}

## Custom R installation

To prepare the custom R installation a couple of folders need to be created prior to the installation of R. Perform the following steps exactly as described:

1. Search for the Command Prompt App by typing `cmd` in the search field of the Windows task bar.

2. The left part of the search results will show the Command Prompt App as best match and it will be highlighted in blue. Click on `Open file location` (third from the top) in the right part displaying the options for the Command Prompt App.

3. A File Explorer window will open with the shortcut to Command Prompt highlighted in blue. Right click the Command Prompt shortcut and select 'WUR - Run with adminstrative rights' as shown in [Figure 8](#figure-explorer_cmd_pusr3) below.

{{< figure src="r-wurclient/file_explorer_cmd.png" caption="Run CMD with 'WUR administrative rights' from File Explorer." numbered="true" id="explorer_cmd_pusr3" >}}

4. The Command Prompt application will open, as shown in [Figure 9](#figure-cmd_prompt3), on the folder `C:\Windows`. The top of the window shows that the Command Prompt application is used in Administrator mode (**<span style="color:red;">WARNING:</span> BE CAREFULL!!**).

{{< figure src="r-wurclient/cmd_with_admin_rights.png" caption="Command Prompt with Adminstrative Rights." numbered="true" id="cmd_prompt3" >}}

5. Create the directory `C:\MyPrograms`. This is done by copying (CTRL+C) the following line, pasting (CTRL+V) it behind the prompt and pressing return (Enter) to execute. In case the directory already exists, the message `A subdirectory or file C:\MyPrograms already exists.` will appear.
```sh
mkdir C:\MyPrograms
```

6. Next create the directory `C:\MyData`. This is done by copying (CTRL+C) the following line, pasting (CTRL+V) it behind the prompt and pressing return (Enter) to execute. In case the directory already exists, the message `A subdirectory or file C:\MyData already exists.` will appear.
```sh
mkdir C:\MyData
```

7. Finally create the directory `C:\ProgramData\R\win-library\4.4`, where user installed packages, via the `install.packages()` command in R, will be stored. The last part of the directory path reflects the major release version of R you are installing and should be adapted for other versions, e.g. for R v4.5.0 the directory created should end with `4.5`.  To create the beforementioned directory copy (CTRL+C) the following line, paste (CTRL+V) it behind the prompt and execute by pressing return (Enter). In case the directory already exists, the message `A subdirectory or file C:\ProgramData\R\win-library\4.4 already exists.` will appear.
```sh
mkdir C:\ProgramData\R\win-library\4.4
```

8. The Command Prompt application can now be closed by typing `exit` and executing it by pressing return (Enter).

### Download
At the time this post was written, the release of R was version 4.0.3. It has been updated to the latest release version 4.4.1 of R.

The installer for Windows 10 can be downloaded directly from this link: [{{< icon name="download" pack="fas" >}} R 4.4.1 for Windows (ca. 82 MB, 64-bit).](https://cloud.r-project.org/bin/windows/base/old/4.4.1/R-4.4.1-win.exe)

{{% callout warning %}}
From R version 4.2.0 the installer is only available for 64-bit Windows 10/11 and will not install on a 32-bit version of the Operating System.
{{% /callout %}}

Save the following files into the Downloads folder of your WURclient desk- or laptop by right-clicking the link and selecting the option 'Save link as...' (**<span style="color:red">IMPORTANT:</span> <u>DO NOT CHANGE THE FILE NAMES!</u>**):

* {{< staticref "files/r/Renviron.site" "newtab" >}}{{< icon name="download" pack="fas" >}} Renviron.site{{< /staticref >}}

* {{< staticref "files/r/Rprofile.site" "newtab" >}}{{< icon name="download" pack="fas" >}} Rprofile.site{{< /staticref >}}

### Installation
The screenshots used below are for R Version 4.0.3. For newer versions of R than 4.0.3 the steps described below are the same and still correct, but start with a newer version of the downloaded executable file of R. The screenshots in this post have not been updated. Therefore, what you see during your installation will differ with respect to the version number shown in the screenshots.

1. Right-click the downloaded file **R-4.4.1-win.exe** and select 'WUR - Run with administrative rights'. This file will most likely reside in your Downloads folder of your user account.
2. If asked for allow to install the software on your computer.
3. After the installer has started, a first selection window will appear as displayed below in [Figure 10](#figure-install_r_language). Select the English language and click the ‘OK’ button to proceed.

{{< figure src="r-wurclient/1-install-r-language.png" caption="R Installation Language Selection." numbered="true" id="install_r_language" >}}

4. Click on the ‘Next’ button to agree to the terms. After this a window will appear, allowing you to select or choose the destination folder, as shown below, where R version 4.4.0 for Windows should be installed. Change the destination location to `C:\MyPrograms\R\R-4.4.1`, as shown in [Figure 11](#figure-install_r_destination) below for version 4.0.3, by typing the destination path directly into the text field displayed (currently showing `C:\Program Files\R\R-4.4.1`) . Click on the ‘Next’ button to continue.

{{< figure src="r-wurclient/2-install-r-destination-folder.png" caption="R Installation Destination Folder Selection." numbered="true" id="install_r_destination" >}}

5. After selecting the installation destination folder the component selector will appear, as displayed below in [Figure 12](#figure-install_r_components). Most desktop and laptop computers these days are using a 64-bit architecture, therefore select (using the pull down menu) the 64-bit User installation as displayed in the image shown below and click on the ‘Next’ button.

{{< figure src="r-wurclient/3-install-r-select-components.png" caption="R Installation Components Selection." numbered="true" id="install_r_components" >}}

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

11. To finalize the custom R installation on your WURclient desk- or laptop copy the files `Renviron.site` and `Rprofile.site` from the Downloads folder on your computer and paste them into the folder named `C:\MyPrograms\R\R-4.4.1\etc`. A window will appear, as displayed below in [Figure 18](#figure-replace_file), to indicate, that the file `Rprofile.site` already exists. Select 'Replace the file in the destination'.

{{< figure src="r-wurclient/replace_rprofile_site_file.png" caption="Replace Rprofile.site File." numbered="true" id="replace_file" >}}

{{% callout note %}}
Congratulations, :satisfied:, you now have R version 4.4.1 installed on your WURclient desktop or laptop computer!
{{% /callout %}}

## Changing the R GUI working directory
<!-- BEFORE September 20, 2023 THIS WAS VALID -->
<!-- HOWEVER, DUE TO PROBLEMS WITH THE KNITR PACKAGE COMPILING TO PDF IT WAS CHANGED -->
<!-- setwd() in Rprofile.site causes the problem -->
<!--
In this custom installation procedure the R HOME directory is set to `C:\MyData`. This means, that at the start the default working directory in R is set to `C:\MyData`. You change this by changing the HOME environment variable in the file `Renviron.site`. The file resides in the `C:\MyPrograms\R\R-4.3.1\etc` directory.

To change the R HOME environment variable perform the following steps:

1. Open a File Explorer and navigate to the `C:\MyPrograms\R\R-4.3.1\etc` folder

2. Right-click the file `Renviron.site` and select the **`Open with`** option. Windows will prompt you to select an application to open the `Renviron.site` file with, as shown below in [Figure 19](#figure-open_with).

{{< figure src="r-wurclient/renviron_site_open_with.png" caption="Open Renviron.site with." numbered="true" id="open_with" >}}

3. First remove the check mark in front of 'Always use this app to open .site files'. Select either Notepad or Wordpad to modify the `Renviron.site` file. When neither is offered, click on the blue text 'More apps' to select either Notepad or Wordpad.

4. Once an editor has been chosen, the file will open in the chosen editor. The first two lines of the 'Renviron.site` file read:
```sh
## Set the user's home directory
HOME='C:/MyData/'
```

5. Modify `'C:/MyData/'` to the preferred startup working directory for R. For example `'M:/My Documents/MyR'` would set the default R working directory to the 'My Documents\MyR' folder of your WUR M:-drive, provided that the folder 'MyR' exists as a sub folder of 'M:\My Documents'. Do not forget to save the file (CRTL+S) to make the change permanent.
-->

When starting the default R GUI the current working directory can be displayed at the R prompt with the command:
```r
getwd()
```

The response at the R prompt will be:
```r
[1] "\\\\WURNET.NL/Homes/user001/My Documents"

```
where `user001` will display your own WUR username.

This could potentially lead to `NormalizePath()` warning messages. Therefore, it is strongly recommended to set the working directory to a mapped drive (shown by a drive letter, e.g., `C:`, or `M:`) in your WURclient. This can be done at the R prompt using the following command, e.g., for setting your working directory to `C:\MyData` or `M:\My Documents`:
```r
setwd("C:\MyData")
# or
setwd("M:\My Documents")
```
No matter which mapped drive and folder you choose, make sure that the location and folder you are providing for the working directory exists!

{{% callout warning %}}
When using the default R GUI, always change the working directory at the start with the `setwd()` function at the R prompt!
{{% /callout %}}

{{% callout note %}}
In earlier versions of this post, the R startup working directory was changed inside the `Rprofile.site` file. This lead to problems when using the `knitr` package to compile to portable document format.

Based on posts by Yihui Xie (the developer of the `knitr` package) the `setwd()` command in `Rprofile.site` has been completely deleted, making knitting to pdf possible again.
<!--Based on posts by Yihui Xie (the developer of the `knitr` package) the `setwd()` command in `Rprofile.site` has been hashed out, making knitting to pdf possible again.-->
{{% /callout %}}
