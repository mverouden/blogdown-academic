---
title: "Anaconda installation on Windows 10/11"
subtitle: ''

# Summary for listings and search engines
summary: Instructions on how to install Anaconda on Windows 10/11.

# Link this post with a project
projects: []

# Date published
date: '2022-11-06'

# Date updated
lastmod: '2022-11-06T15:24:05+02:00'

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
  - Windows 10
  - Windows 11

categories:
  - Anaconda
  - Windows 10
  - Windows 11
  - WUR

slug: anaconda-installation-windows-10-11

share: true
---

{{% toc %}}

## Motivation
<!--Due to the novel coronavirus (SARS-CoV-2) and its related disease :mask: COVID-19 employees and students at Wageningen University & Research are all working from home.-->

Whether working, or studying, everybody uses various sorts and types of software on their computer. Around 34 courses at Wageningen University & Research use Anaconda Python as software in their course, e.g., [SSB30806 Modelling in Systems Biology](https://wur.osiris-student.nl/#/onderwijscatalogus/extern/cursus?cursuscode=SSB30806&collegejaar=huidig), and [SSB32806 Introduction to Systems and Synthetic Biology](https://wur.osiris-student.nl/#/onderwijscatalogus/extern/cursus?cursuscode=SSB32806&collegejaar=huidig).

{{% callout note %}}
This post will show how to install Anaconda Python (Anaconda3) on a **privately owned** desktop or laptop computer running Windows 10 or Windows 11 as operating system.
{{% /callout %}}

{{% callout warning %}}
The installation instructions in this post are <u>**not to be used on WURclient desktops or laptops**</u>! For a WURclient desktop or laptop see the post: [Custom Anaconda installation on a WURclient compute](/post/2022/11/03/anaconda-installation-wurclient/).
{{% /callout %}}

Two ways to install Anaconda are offered here:

1. [WUR AppStore](#1-wur-appstore). This is the **RECOMMENDED** way!
2. [Manual installation](#2-manual-installation) for those who, for whatever reason, do not want to use the WUR AppStore.

## 1. WUR AppStore
The WUR AppStore is the place where you will be able to download, link to, or virtually access the software you need for your study programme and courses. Not only during the computer labs and courses, but also for self-study after those. 

For more information see: [What is the WUR AppStore](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1222947-what-is-the-wur-appstore)

### Windows 10/11 compatibility and WUR AppStore installation

* To safely use the study and course software, you need to **connect your laptop to the WUR** network with your WUR account. **Windows 10 or 11 Education Edition** or  **Professional Edition** is needed on your laptop to be able to access the WUR AppStore. If you are using a Home Edition of Windows 10 or 11, you will be automatically upgraded to the Education Edition.
*  If you have Windows 10 or 11, you can proceed to the manual: [How to connect to the WUR AppStore](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1203863-how-to-connect-to-the-wur-appstore).
<!--* If you have another version of Windows 10/11 (e.g. Windows 10/11 Home), follow the manual: [How to get Windows 10 Education](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1223173-how-to-get-windows-10-education). After having upgraded Windows 10 to the Education version, you can proceed to the manual: [How to get access to the WUR AppStore](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1203863-how-to-connect-to-the-wur-appstore).-->

### Using the WUR AppStore
The use of the WUR AppStore is very well described by the WUR TEAM Study Anytime, Anyplace. The first article can be found here: [How can I use the WUR AppStore](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1203865-how-can-i-use-the-wur-appstore)

The WUR AppStore currently contains **Anaconda3 2025.06-0**.<!-- Before the start of Academic Year 2025-2026 **Anaconda 2025.06-0** will be made available!-->

### Support WUR AppStore
In case you need support installing or using the WUR AppStore you can contact the WUR Servicedesk IT either by telephone: <a href="tel:+31317488888">+31 (0)317 488888</a> / mail: <a href="mailto:Servicedesk.IT@wur.nl">Servicedesk.IT AT wur.nl</a>. You can also visit the Servicepoint IT, ground floor left of the Grand Café, in Forum (Building 102) on the WUR Campus.

## 2. Manual Installation

By default the Anaconda installer wants to install into the `C:\ProgramData` folder of your Windows Operating System. According to Microsoft this folder is "used by applications to store data for standard users, because it does not require elevated permissions". However, it is not recommended to use for installing software. The reason, the Anaconda installer chooses this folder, is that it does not contain a whitespace character like in `C:\Program Files\`. The Anaconda software can not deal with whitespace characters in path names, while running.

To prepare the Anaconda installation a folder needs to be created prior to the installation of Anaconda. Either create the folder `C:\MyPrograms` yourself in File Explorer, or perform the following steps exactly as described:

1. Search for the Command Prompt App by typing `cmd` in the search field of the Windows task bar. Press return (Enter) to start the application. A window will appear similar to as displayed in [Figure 1](#figure-command_promt) showing your own system username.

{{< figure src="anaconda-windows/1-command-prompt.png" caption="Windows Command Prompt Application window" numbered="true" id="command_prompt" >}}

2. Create the directory `C:\MyPrograms`. This is done by copying (CTRL+C) the following line, pasting (CTRL+V) it behind the prompt and pressing return (Enter) to execute. In case the directory already exists, the message `A subdirectory or file C:\MyPrograms already exists.` will appear.
```sh
mkdir C:\MyPrograms
```

3. The Command Prompt application can now be closed by typing `exit` and executing it by pressing return (Enter).

### Download
At the time this post was written, the latest release of Anaconda3 was version 2022.10. It has been updated to the latest release version `2025.06-1` of Anaconda3.

The installer for Windows 10/11 can be downloaded directly from this link: [{{< icon name="download" pack="fas" >}} Anaconda3 2025.06-1 for Windows (ca. 914.6 MB, 64-bit).](https://repo.anaconda.com/archive/Anaconda3-2025.06-1-Windows-x86_64.exe)

{{% callout warning %}}
From Anaconda3 version 2022.10 the installer is only available for 64-bit Windows 10/11 and will not install on a 32-bit version of the Operating System.
{{% /callout %}}


### Installation
For newer versions of Anaconda3 than 2022.10 the steps described below are the same and still correct, but start with a newer version of the downloaded executable installer file of Anaconda3. The screenshots in this post have not been updated. Therefore, what you see during your installation will differ with respect to the version number shown in the screenshots.

1. Right-click the downloaded file **Anaconda3-2025.06-1-Windows-x86_64.exe** and select 'Run as administrator', as shown in [Figure 2](#figure-start_admin). This file will most likely reside in your Downloads folder of your user account.

{{< figure src="anaconda-windows/2-start-installer-as-admin.png" caption="Start Anaconda Installer as administrator" numbered="true" id="start_admin" >}}

2. Windows will ask for permission to allow the application to make changes to your device as shown in [Figure 3](#figure-allow_changes_installer). Click 'Yes' to continue.

{{< figure src="anaconda-windows/3-allow-changes-anaconda.png" caption="Permission request for changes." numbered="true" id="allow_changes_installer" >}}

3. After the installer has started, a first selection window will appear as displayed below in [Figure 4](#figure-welcome_anaconda_setup). Click the ‘Next >’ button to proceed.

{{< figure src="anaconda-windows/4-welcome-installer-anaconda.png" caption="Welcome to Anaconda3 2022.10 (64-bit) Setup." numbered="true" id="welcome_anaconda_setup" >}}

4. The installer will now display the license agreement for installation of Anaconda3, as shown below in [Figure 5](#figure-agreement_anaconda_setup). Click on the ‘I Agree’ button to agree to the terms.

{{< figure src="anaconda-windows/5-license-agreement-anaconda.png" caption="Anaconda3 Setup License Agreement" numbered="true" id="agreement_anaconda_setup" >}}

5. After agreeing to the license terms, the Anaconda3 setup will ask for whom you wish to install for, as displayed in [Figure 6](#figure-install_for). Select the radio button ‘All Users (requires admin priveleges)’ and click on the ‘Next >’ button to proceed.

{{< figure src="anaconda-windows/6-selection-installation-type.png" caption="Anaconda3 Setup Select Installation Type" numbered="true" id="install_for" >}}

6. Having selected the installation type, the Anaconda3 setup will request for an installation location as shown in [Figure 7](#figure-install_location). Change the destination location to `C:\MyPrograms\Anaconda3`, to match [Figure 7](#figure-install_location), by typing the destination path directly into the text field displayed (currently showing `C:\ProgramData\Anaconda3`). Click on the ‘Next >’ button to continue.

{{< figure src="anaconda-windows/7-choose-install-location.png" caption="Anaconda3 Setup Choose Installation Location" numbered="true" id="install_location" >}}

7. After selecting the installation location folder the Advanced Installation Options will appear, as displayed below in [Figure 8](#figure-advanced_options). Leave the selection as displayed and click on the ‘Install’ button to start the installation.

{{< figure src="anaconda-windows/8-advanced-installation-options.png" caption="Anaconda3 Setup Advanced Installation Options" numbered="true" id="advanced_options" >}}

8. Once the installation has been completed [Figure 9](#figure-installation_complete) will be displayed. Click on the ‘Next >’ button to continue.

{{< figure src="anaconda-windows/9-installation-complete.png" caption="Anaconda3 Setup Installation was completed successfully" numbered="true" id="installation_complete" >}}

9. Next the Anaconda3 Setup will show some information on how great Anaconda works with DataSpell, as shown in [Figure 10](#figure-anaconda_ds). Click the 'Next >' button to proceed.

{{< figure src="anaconda-windows/10-message-dataspell.png" caption="Anacond3 Setup message about Anaconda and DataSpell" numbered="true" id="anaconda_ds" >}}

10. Finally the Annaconda 3 Setup shows that installation has been completed as displayed in [Figure 11](#figure-anaconda_completing). Remove the tick marks from the boxes in front of 'Anaconda Distribution Tutorial' and 'Getting Started with Anaconda', unless you want to display this information, click the 'Finish' button to finish off the installation and close the Anaconda3 Setup.

{{< figure src="anaconda-windows/11-finish-installer-anaconda.png" caption="Completing Anacond3 Setup" numbered="true" id="anaconda_completing" >}}

{{% callout note %}}
Congratulations, :satisfied:, you now have Anaconda3 version 2025.06-1 containing Python 3.13.5 installed on your Windows desktop or laptop computer!
{{% /callout %}}

{{% callout warning %}}
Below in [Configuration Anaconda3](#configuration-anaconda3) you find information about additional tasks you may need to perform. 

Use the ones required!
{{% /callout %}}

## Configuration Anaconda3

### Upgrading Anaconda Navigator (Anaconda3)

When starting Anaconda Navigator from your Start Menu the Navigator may open displaying the message shown in [Figure 12](#figure-navigator_upgrade).

{{< figure src="anaconda-windows/12-upgrade-navigator.png" caption="Upgrade available for Anaconda Navigator" numbered="true" id="navigator_upgrade" >}}

To upgrade Anaconda Navigator follow these steps:

1. Click on 'Yes' as shown in [Figure 12](#figure-navigator_upgrade).

2. Windows will ask for permission to allow the application to make changes to your device as shown in [Figure 13](#figure-allow_changes_update). Click 'Yes' to continue.

{{< figure src="anaconda-windows/13-allow-app-changes.png" caption="Permission request for changes to update." numbered="true" id="allow_changes_update" >}}

3. Continue the procedure as indicated on your display to perform the update of Anaconda Navigator.

### Add a R kernel

After installing Anaconda3 only the Python kernel is present. To add a R kernel for use inside Jupyter Notebook or JupyterLab perform the following steps:

1. Open the Start Menu and navigate to 'Anaconda3 (64-bit)'.

2. Start 'Anaconda Powershell Prompt (Anaconda3)'. A window will open displaying the prompt as `(base) PS C:\>`.

3. Navigate to where `R.exe` is located. Let's assume you have R v4.2.1 installed, either via the WUR AppStore or via [R installation on Windows 10/11](/post/2020/04/06/r-installation-windows-10/). For other R versions than 4.2.1 do not forget to change the R version number!

    + Use the following commands:
    
      ```sh
       cd C:\Program Files\R\R-4.2.1\bin\
       .\R.exe
       ## At the R prompt, indicated by >
       install.packages("IRkernel")
       IRkernel::installspec()
       q()
       # Question in R: Save workspace image? [y/n/c]: n
       ## back at the powershell prompt, indicated by (base) PS C:\>
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
