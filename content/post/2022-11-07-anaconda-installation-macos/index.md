---
title: "Anaconda (re-)installation on macOS"
subtitle: ''

# Summary for listings and search engines
summary: Instructions on how to install Anaconda on macOS.

# Link this post with a project
projects: []

# Date published
date: '2022-11-07'

# Date updated
lastmod: '2022-11-07T09:20:00+02:00'

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
  - Anaconda
  - macOS

categories:
  - Anaconda
  - macOS
  - WUR

slug: anaconda-installation-macos

share: true
---

{{% toc %}}

## Motivation
<!--Due to the novel coronavirus (SARS-CoV-2) and its related disease :mask: COVID-19 employees and students at Wageningen University & Research are all working from home.-->

Whether working or studying everybody uses various sorts and types of software on their computer. Around 34 courses at Wageningen University & Research use Anaconda Python as software in their course, e.g. [SSB-30806 Modelling in Systems Biology](https://wur.osiris-student.nl/#/onderwijscatalogus/extern/cursus?cursuscode=SSB30806&collegejaar=huidig) and [SSB-50806 Systems and Synthetic Biology](https://wur.osiris-student.nl/#/onderwijscatalogus/extern/cursus?cursuscode=SSB50806&collegejaar=huidig).

{{% callout note %}}
The instructions in this post will show how to install Anaconda on a desktop or laptop computer running macOS as operating system.
{{% /callout %}}

In the text some symbol combinations are used for shortcuts, the following table explains the meaning of these symbols in relation to specific keys on your keyboard. To use the shortcuts press the keyboard keys simultaneously, e.g. &#8679;&#8984;A means &#8679;+&#8984;+A.

|  Icon   | &nbsp; | Keyboard Meaning             | &nbsp;&nbsp; |  Icon   | &nbsp; | Keyboard Meaning               |
|:-------:|:------:|:-----------------------------|:------------:|:-------:|:------:|:-------------------------------|
| &#8984; | &nbsp; | command                      | &nbsp;&nbsp; | &#8682; | &nbsp; | caps lock                      |
| &#8997; | &nbsp; | option (or alt)              | &nbsp;&nbsp; | &#8617; | &nbsp; | carriage return (return/enter) |
| &#8963; | &nbsp; | control                      | &nbsp;&nbsp; | &#9003; | &nbsp; | delete/backspace               |
| fn      | &nbsp; | function                     | &nbsp;&nbsp; | &#8998; | &nbsp; | forward delete (fn + &#9003;)  |
| &#8679; | &nbsp; | shift (either left or right) | &nbsp;&nbsp; | &#9099; | &nbsp; | escape                         |

## Complete removal of a previous Anaconda installation on macOS
If you have previously installed Anaconda and wish to re-install the latest version or your current installation is not working as you expect, you first need to delete everything related to Anaconda. In macOS a complete removal is somewhat complicated, but doable if you follow all steps precisely as provided in this post.

For the complete removal of everything related to Anaconda the Terminal application will be used. In your Finder > Applications (shortcut: &#8679;&#8984;A) there is a Utilities folder as depicted in [Figure 1](#figure-utilities_folder) below.

{{< figure src="anaconda-macos/macos-utilities-icon.png" caption="Finder Utilities Folder." numbered="true" id="utilities_folder" >}}

Within this Utilities folder, which can be directly accessed by using the &#8679;&#8984;U shortcut, the Terminal application is contained. The icon in [Figure 2](#figure-terminal_app) shows what the Terminal application looks like in the Finder > Applications > Utilities folder.

{{< figure src="anaconda-macos/macos-terminal-icon.png" caption="Icon Terminal Application." numbered="true" id="terminal_app" >}}

The Terminal application can also be started via Lauchpad under the ‘Other’ group.

Steps for a complete removal of Anaconda on macOS:

1. Start the Terminal application. The terminal console prompt, where the commands will be entered, is depicted by a `%` or a `$` sign. Which sign is shown, depends whether your default shell is zsh (`%` sign) or bash (`$` sign).

2. Install the `anaconda-clean` package:

    ```sh
    conda install anaconda-clean
    ```

3. Then, run `anaconda-clean` with the argument `--yes` to remove all those files and directories without being asked to confirm each one:

    ```sh
    anaconda-clean --yes
    ```

{{% callout note %}}
`anaconda-clean --yes` creates a backup of all files and directories that might be removed in a folder named `.anaconda_backup` in your home directory. Also note that `anaconda-clean` leaves your data files in the AnacondaProjects directory untouched.
{{% /callout %}}

4. Remove all Anaconda directories from your system by sequentially executing the following commands:

    ```sh
    rm -rf /Applications/Anaconda-Navigator.app
    sudo rm -rf /opt/anaconda3
    rm -rf ~/.anaconda_backup
    ```

5. Sequentially open `.bash_profile`, `tcshrc`, `.xonshrc`, and `.zshrc` in TextEdit and delete the section starting with `# >>> conda initialize >>>` and ending with `# <<< conda initialize <<<`.

In a terminal this is done, e.g. for `.bash_profile`, with `open -a TextEdit .bash_profile`. Use the shortcut &#8984;S to save the file, and close the file with the shortcut &#8984;Q.

{{% callout note %}}
Having performed all 5 steps given above, your mac will be ready for a new installation of Anaconda.
{{% /callout %}}

## Download 
At the time this post was written, the latest release of Anaconda was version 2022.10 containing Python 3.9.13. It has been updated to the latest release version `2024.10-1` of Anaconda containing Python 3.12.7.

For newer versions of Anaconda than 2022.10 the steps described below are the same and still correct, but start with a newer version of the downloaded installer package file of Anaconda. The screenshots in this post have not been updated. Therefore, what you see during your installation can (and probably will) differ with respect to the version number shown in the screenshots.

{{% callout warning %}}
For macOS there are two downloads of Anaconda available on the [Anaconda Repository Archive](https://repo.anaconda.com/archive/). To see which version you need click on {{< icon name="apple" pack="fab" >}} in the menu bar and select ‘About This Mac’.

__NOTE__: If you are using a mac with the newest M1, M2 or M3 processor, download the __Apple Silicon arm64__ build!
{{% /callout %}}

Download Anaconda for your specific version of macOS using one of the following links:

- For an Intel processor based mac: [{{< icon name="download" pack="fas" >}} Anaconda3 2024.10-1 (ca. 776.0 MB, __Intel 64-bit__ build)](https://repo.anaconda.com/archive/Anaconda3-2024.10-1-MacOSX-x86_64.pkg)
- For a M1/M2/M3 processor based mac: [{{< icon name="download" pack="fas" >}} Anaconda3 2024.10-1 (ca. 744.6 MB, __ARM 64-bit__ build)](https://repo.anaconda.com/archive/Anaconda3-2024.10-1-MacOSX-arm64.pkg)

## Installation

For installing Anaconda on macOS follow these steps:

1. Open the downloaded file, either **Anaconda3-2024.10-1-MacOSX-x86_64.pkg**, or **Anaconda3-2024.10-1-MacOSX-arm64.pkg** depending on the processor in your mac (as explained above). This file will most likely reside in Finder > Downloads (shortcut: &#8997;&#8984;L). The file can more easily be found by switching into List view (shortcut: &#8984;2). To switch to Icon view use the shortcut: &#8984;1.

2. The installler will start by displaying a message as shown in [Figure 3](#figure-allow-install). Click 'Allow' to let the package determine if the software can be installed.

{{< figure src="anaconda-macos/1-allow-install.png" caption="Determine whether package can be installed." numbered="true" id="allow-install" >}}

3. When the package can be installed the welcome screen of the Anaconda3 Installer will be displayed as shown in [Figure 4](#figure-welcome-installer). Click the 'Continue' button to proceed with the installation.

{{< figure src="anaconda-macos/2-welcome-installer.png" caption="Welcome Anaconda3 Installer." numbered="true" id="welcome-installer" >}}

4. Now the Read Me for the software to be installed as displayed in [Figure 5](#figure-install-readme) below. Click the ‘Continue’ button to proceed.

{{< figure src="anaconda-macos/3-read-me-installer.png" caption="Anaconda3 Installer Read Me." numbered="true" id="install-readme" >}}

4. Right after the Read Me a Software Licence Agreement will appear as shown in [Figure 6](#figure-license-terms). By clicking the ‘Continue’ button you will be asked to agree with this software licence agreement as diplayed below in [Figure 7](#figure-license-agree). Click on ‘Agree’ to proceed.

{{< figure src="anaconda-macos/4-license-agreement.png" caption="Aanconda3 Software License Agreement." numbered="true" id="license-terms" >}}

{{< figure src="anaconda-macos/5-agree-to-terms.png" caption="Agree to Software License Agreement." numbered="true" id="license-agree" >}}

5. The installer will let you select how you want to install the software as shown in [Figure 8](#figure-install-type). It is recommended to leave the settings as provided and click the 'Continue' button.

{{< figure src="anaconda-macos/6-installation-type.png" caption="Select the installation type." numbered="true" id="install-type" >}}

6. After selecting the installation type the installer asks to provide an installation destination as displayed in [Figure 9](#figure-install-location). Also here it is recommended to leave the default settings and click the 'Install' button.

{{< figure src="anaconda-macos/7-installation-location.png" caption="Select the installation location." numbered="true" id="install-location" >}}

7. Your system will ask to either provide the password (see [Figure 10](#figure-confirm-installation)) or use the fingerprint scanner to confirm the software installation.

{{< figure src="anaconda-macos/8-confirm-installation.png" caption="Confirm the software installation." numbered="true" id="confirm-installation" >}}

8. Your system may ask you to allow access to your Downloads folder, as shown in [Figure 11](#figure-allow-downloads). Click the 'OK' button to grant access to the Downloads folder.

{{< figure src="anaconda-macos/9-allow-access.png" caption="Allow access to the Downloads folder." numbered="true" id="allow-downloads" >}}

9. Once the files have been installed the Anaconda3 installer will display a message about DataSpell as shown in [Figure 12](#figure-dataspell). If your interested visit [https://www.anaconda.com/dataspell]. To proceed with the installer click the 'Continue' button.

{{< figure src="anaconda-macos/10-dataspell-message.png" caption="Message about DataSpell." numbered="true" id="dataspell" >}}

10. After the DataSpell message the Anaconda3 installer has reached the end (see [Figure 13](#figure-finish)). Click on the 'Close' button to finalize the installer and close the installer.

{{< figure src="anaconda-macos/11-installation-finish.png" caption="Finish and close the Anaconda3 installer." numbered="true" id="finish" >}}

{{% callout note %}}
Congratulations :satisfied:, you now have Anaconda3 2024.10-1 containing Python 3.12.7 installed on your mac!

Before actively using Anaconda, some configuration may be required. The configuration is described in the next section.
{{% /callout %}}

## Configuration Anaconda3

### Upgrading Anaconda Navigator (Anaconda3)

When starting Anaconda Navigator from your Applications folder, the Navigator may open displaying the message shown in [Figure 14](#figure-navigator-upgrade).

{{< figure src="anaconda-macos/12-upgrade-navigator.png" caption="Upgrade available for Anaconda Navigator" numbered="true" id="navigator-upgrade" >}}

To upgrade Anaconda Navigator follow these steps:

1. Click on 'Yes' as shown in [Figure 14](#figure-navigator-upgrade).

2. Continue the procedure as indicated on your display to perform the update of Anaconda Navigator.

### Add a R kernel

After installing Anaconda3 only the Python kernel is present. To add a R kernel for use inside Jupyter Notebook or JupyterLab perform the following steps:

1. Open the Terminal application as described above in [Complete removal of a previous Anaconda installation on macOS](#complete-removal-of-a-previous-anaconda-installation-on-macos).

2. Start R by typing `R` and press return &#8617; to execute.

3. Add the R prompt type the following commands sequentially and after each command press return &#8617; to execute. Below version 4.2.1 of R is assumed, do not forget to change the R version number when you are using a different version of R!

      ```sh
       ## At the R prompt, indicated by >
       install.packages("IRkernel")
       IRkernel::installspec()
       q()
       # Question in R: Save workspace image? [y/n/c]: n
      ```

4. Close the Terminal application by typing `exit` and press return &#8617; to execute.

Now the R kernel will be available in Jupyter Notebook and JupyterLab.

### Add a Julia kernel

After installing Anaconda3 only the Python kernel is present, unless you already have [added a R kernel](#add-a-r-kernel). To add a Julia kernel for use inside Jupyter Notebook or JupyterLab perform the following steps:

1. Open the Terminal application as described above in [Complete removal of a previous Anaconda installation on macOS](#complete-removal-of-a-previous-anaconda-installation-on-macos).

2. Start Julia by typing `julia` at the terminal prompt and press return &#8617; to execute. Once Julia has started, you will see the prompt displayed as `julia>`.

3. Type `]` and the prompt will change into `(@v1.8) pkg>`. This under the assumption that you have Julia v1.8.2 or later installed. For other versions of Julia the version number for package management will differ.

4. Type the command `add IJulia` and press return &#8617; to execute. This will install a lot of packages and make the Julia kernel available in Jupyter Notebook and JupyterLab.

5. Close the Julia package manager by pressing the BACKSPACE key on your keyboard.

6. Type `exit()` and press return &#8617; to execute, in order to close Julia.

7. Close the Terminal application by typing `exit` and press return &#8617; to execute.

Now the Julia kernel will be available in Jupyter Notebook and JupyterLab.
