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

This version of Anaconda Python was packaged for educational purposes. Only once per year a new version of Anaconda Python is released in Software Center and simultaneously in the WUR AppStore (course software for students).

Many users, however, would like to use a newer version of Anaconda Python than the one in Software Center. At the moment of writing this post the latest version of Anaconda Python released on the [Anaconda Repository Archive](https://repo.anaconda.com/archive/) is Anaconda3 version 2022.10 containing Python 3.9.13 (released on 2022-10-17). <!--The post has been updated, with the exception of the screenshots, to R version 4.2.2 named: "Innocent and Trusting". -->

{{% callout note %}}
This post will show how to custom install Anaconda Python on a **WURclient** desktop or laptop computer without using Software Center.
{{% /callout %}}

{{% callout warning %}}
The installation instructions in this post are <u>**not to be used on privately owned desktops or laptops**</u>!<!-- For a privately owned desktop or laptop see the post: [Anaconda installation on Windows 10/11](/post/2020/04/06/r-installation-windows-10/).-->
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

7. Once the installation has been completed [Figure 13](#figure-installation_complete) will be displayed. Click on the ‘Next >’ button to continue.

{{< figure src="anaconda-wurclient/11-installation-complete.png" caption="Anaconda3 Setup Installation was completed successfully" numbered="true" id="installation_complete" >}}

8. Next the Anaconda3 Setup will show some information on how great Anaconda works with DataSpell as shown in [Figure 14](#figure-anaconda_ds). Click the 'Next >' button to proceed.

{{< figure src="anaconda-wurclient/12-anaconda-jetbrains.png" caption="Anacond3 Setup message about Anaconda and DataSpell" numbered="true" id="anaconda_ds" >}}

9. Finally the Annaconda 3 Setup shows that installation has been completed as displayed in [Figure 15](#figure-anaconda_completing). Remove the tick marks from the boxes in front of 'Anaconda Distribution Tutorial' and 'Getting Started with Anaconda', unless you want to display this information, click the 'Finish' button to finish off the installation and close the Anaconda3 Setup.

{{< figure src="anaconda-wurclient/13-finish-installer-anaconda.png" caption="Completing Anacond3 Setup" numbered="true" id="anaconda_completing" >}}

{{% callout note %}}
Congratulations, :satisfied:, you now have Anaconda3 version 2022.10 containing Python 3.9.13 installed on your WURclient desktop or laptop computer!
{{% /callout %}}

{{% callout warning %}}
Before using Anaconda check out the configuration instructions below carefully.

At least do the part on [Changing the Default Startup Working Directory](#changing-the-default-startup-working-directory)!
{{% /callout %}}

## Configuration Anaconda3

<!-- ORIGINAL: C:\MyPrograms\Anaconda3\python.exe C:\MyPrograms\Anaconda3\cwp.py C:\MyPrograms\Anaconda3 C:\MyPrograms\Anaconda3\python.exe C:\MyPrograms\Anaconda3\Scripts\jupyter-notebook-script.py "%USERPROFILE%/" -->

<!-- CHANGED WITH ADMIN RIGHTS TO: C:\MyPrograms\Anaconda3\python.exe C:\MyPrograms\Anaconda3\cwp.py C:\MyPrograms\Anaconda3 C:\MyPrograms\Anaconda3\python.exe C:\MyPrograms\Anaconda3\Scripts\jupyter-notebook-script.py "M:\My Documents" -->

### Changing the Default Startup Working Directory

When starting JupyterLab or Jupyter Notebook from within Anaconda Navigator the default working directory on a WURclient will be `C:\User\user001`, where `user001` will display your own WUR username. This is not a very smart location to store your Jupyter Notebook files (files with the `*.ipynb` extension), because this a local storage location without backup.

Most users would like to store their documents in `M:\My Documents`, which is an internal mapping to `\\WURNET.NL\Homes\user001\Documents`. Files stored in your `M:\`-drive are backed up by FB-IT and, therefore, provide a much safer storage environment.

To change the default start up working directory perform the following steps:

1. Open the Start Menu and navigate to 'Anaconda3 (64-bit)'.

2. Either start 'Anaconda Powershell Prompt (Anaconda3)' or 'Anaconda Prompt (Anaconda3)'. A window will open displaying the prompt as `(base) PS C:\>` for 'Anaconda Powershell', or `(base) C:\>` for 'Anaconda Prompt`.

3. Type the command shown below behind the prompt and press return (Enter) to execute:
```sh
jupyter notebook --generate-config
```

4. A message stating: `Writing default config to: C:\Users\user001\.jupyter\jupyter_notebook_config.py`, where `user001` will display your own WUR username, is printed in the window. Type `exit` and press return (Enter) to close the prompt window.

5. Open a File Explorer window and navigate to the created file `C:\Users\verou004\.jupyter\jupyter_notebook_config.py`. You may have to change the settings in File Explorer to show the hidden items (File Explorer top menu bar 'View' and place a tick mark in front of 'hidden items').

6. Right-click the file `jupyter_notebook_config.py` and select '**Open with**'. Remove the tick mark in front of 'Always use this app to open .py files' and select e.g. 'Notepad'. If you do not see 'Notepad', click on 'More apps'.

7. The file `jupyter_notebook_config.py` will open in the 'Notepad' application. Navigate to line 393 (press `CTRL+G` and enter 393). Remove the `#` and whitespace character in front of `c.NotebookApp.notebook_dir` and replace `''` with `'M:\My Documents'`. Save the document by press `CTRL+S`. Lines 391-393 should now look like this:
```sh
## The directory to use for notebooks and kernels.
#  Default: ''
c.NotebookApp.notebook_dir = 'M:\My Documents'
```

8. Make sure you have saved your changes in the file `jupyter_notebook_config.py` and close the 'Notepad` application.

You have now changed the default start up working directory permanently.

### Upgrading Anaconda Navigator (Anaconda3)

When after starting Anaconda Navigator sometimes you will see that a newer version of the Navigator is available. In the top right corner this is indicated as displayed in [Figure 16](#figure-navigator_upgrade)

{{< figure src="anaconda-wurclient/14-upgrade-navigator.png" caption="Upgrade available for Anaconda Navigator" numbered="true" id="navigator_upgrade" >}}

However, having started Anaconda Navigator from the Start Menu as regular user, you will be prompted to enter the administrator username and password. This is a problem, because you are a Power User and not an Administrator.

To be able to upgrade Anaconda Navigator you have to start the application with 'WUR - Run with adminstrative rights'. This can be done by following these steps:

1. Open the Start Menu and navigate to 'Anaconda3 (64-bit)'

2. Right-click on the 'Anaconda Navigator (Anaconda3)' start item, select 'More' > 'Open file location'. This will open a File Explorer window displaying the shortcuts to start items of 'Anaconda3 (64-bit)'.

3. Again right-click on the start item "Anaconda Navigator (Anaconda3)" in the File Explorer windows and select 'WUR - Run with adminstrative rights'

Now you will be able to upgrade Anaconda Navigatore by clicking on 'Upgrade Now', as displayed in [Figure 16](#figure-navigator_upgrade).

### Add a R kernel

After installing Anaconda3 only the Python kernel is present. To add a R kernel for use inside Jupyter Notebook or JupyterLab perform the following steps:

1. Open the Start Menu and navigate to 'Anaconda3 (64-bit)'.

2. Start 'Anaconda Powershell Prompt (Anaconda3)'. A window will open displaying the prompt as `(base) PS C:\>`.

3. Navigate to where `R.exe` is located. Let's assume you have R v4.2.1 installed, either via Software Center or via [Custom installation on a WURclient](/post/2021/01/24/r-installation-wurclient/)). For other R versions than 4.2.1 do not forget to change the R version number!

    + For a installation via Sofware Center use the following commands:
    
      ```sh
       cd C:\Program Files\R\R-4.2.1\bin\
       .\R.exe
       # At the R prompt, indicated by >
       install.packages("IRkernel")
         IRkernel::installspec()
       q()
       Save workspace image? [y/n/c]: n
       # back at the powershell prompt, indicated by (base) PS C:\>
       exit
      ```

    + For a [Custom installation on a WURclient](/post/2021/01/24/r-installation-wurclient/) use the following commands:
    
      ```sh
       cd C:\MyPrograms\R\R-4.2.1\bin\
       .\R.exe
       # At the R prompt, indicated as >
       install.packages("IRkernel")
       IRkernel::installspec()
       q()
       Save workspace image? [y/n/c]: n
       # back at the powershell prompt, indicated by (base) PS C:\>
       exit
      ```

Now the R kernel will be available in Jupyter Notebook and JupyterLab.

### Add a Julia kernel

After installing Anaconda3 only the Python kernel is present, unless you already did [Add a R kernel](#add-a-r-kernel) . To add a Julia kernel for use inside Jupyter Notebook or JupyterLab perform the following steps:

1. Open Julia on your WURclient. A window will open and you will see the prompt displayed as `julia>`
2. Type `]` and the prompt will change into `(@v1.8) pkg>`. This under the assumption that you have Julia v1.8.2 or later installed. For other versions of Julia the version number for package management will differ.
3. Type the command `add IJulia`. This will install a lot of packages and make the Julia kernel available in Jupyter Notebook and JupyterLab.
4. Close the Julia package manager by pressing the BACKSPACE key on your keyboard.
5. Type `exit()` to close Julia.

Now the Julia kernel will be available in Jupyter Notebook and JupyterLab.
