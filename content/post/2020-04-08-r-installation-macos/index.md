---
title: "(re-)Installation and Configuration of R on macOS"
subtitle: ''

# Summary for listings and search engines
summary: Instructions on how to (re-)install R on macOS.

# Link this post with a project
projects: []

# Date published
date: '2020-04-08'

# Date updated
lastmod: '2022-05-30T19:01:4+02:00'

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
  - Reinstallation
  - R
  - macOS

categories:
  - R
  - macOS
  - WUR

slug: r-installation-macos

share: true
---

{{% toc %}}

## Motivation
<!--Due to the novel coronavirus (SARS-CoV-2) and its related disease :mask: COVID-19 employees and students at Wageningen University & Research are all working from home.-->

Whether working or studying everybody uses various sorts and types of software on their computer. Students taking [Statistical Courses, as taught by the Mathematical and Statistical Methods group at Wageningen University & Research](https://www.wur.nl/en/Research-Results/Research-Institutes/plant-research/biometris/Education/BSc-and-Master-Courses.htm), will most likely use R.

{{% callout note %}}
The instruction in this post will show how to (re-)install R on a desktop or laptop computer running macOS as operating system.
{{% /callout %}}

In the text some symbol combinations are used for shortcuts, the following table explains the meaning of these symbols in relation to specific keys on your keyboard. To use the shortcuts press the keyboard keys simultaneously, e.g. &#8679;&#8984;A means &#8679;+&#8984;+A.

|  Icon   | &nbsp; | Keyboard Meaning             | &nbsp;&nbsp; |  Icon   | &nbsp; | Keyboard Meaning               |
|:-------:|:------:|:-----------------------------|:------------:|:-------:|:------:|:-------------------------------|
| &#8984; | &nbsp; | command                      | &nbsp;&nbsp; | &#8682; | &nbsp; | caps lock                      |
| &#8997; | &nbsp; | option (or alt)              | &nbsp;&nbsp; | &#8617; | &nbsp; | carriage return (return/enter) |
| &#8963; | &nbsp; | control                      | &nbsp;&nbsp; | &#9003; | &nbsp; | delete/backspace               |
| fn      | &nbsp; | function                     | &nbsp;&nbsp; | &#8998; | &nbsp; | forward delete (fn + &#9003;)  |
| &#8679; | &nbsp; | shift (either left or right) | &nbsp;&nbsp; | &#9099; | &nbsp; | escape                         |

## Completely removing R from macOS
If you have previously installed R and wish to re-install the latest version or your current installation is not working as you expect, you first need to delete everything related to R. In macOS a complete removal is somewhat complicated, but doable if you follow all steps precisely as provided in this post.

For the complete removal of everything related to R the Terminal application will be used. In your Finder > Applications (shortcut: &#8679;&#8984;A) there is a Utilities folder as depicted in [Figure 1](#figure-utilities_folder) below.

{{< figure src="r-macos/macos-utilities-icon.png" caption="Finder Utilities Folder." numbered="true" id="utilities_folder" >}}

Within this Utilities folder, which can be directly accessed by using the &#8679;&#8984;U shortcut, the Terminal application is contained. The icon in [Figure 2](#figure-terminal_app) shows what the Terminal application looks like in the Finder > Applications > Utilities folder.

{{< figure src="r-macos/macos-terminal-icon.png" caption="Icon Terminal Application." numbered="true" id="terminal_app" >}}

The Terminal application can also be started via Lauchpad under the ‘Other’ group.

Steps for a complete removal of R on macOS:

1. Start the Terminal application. The terminal console prompt, where the commands will be entered, is depicted by a `%` or a `$` sign. Which sign is shown, depends whether your default shell is zsh (`%` sign) or bash (`$` sign).
2. To delete the R application copy (&#8984;C) the following line, paste (&#8984;V) it behind the terminal console prompt and press return (&#8617;) to execute. Provide the macOS password when asked (the typed password will not be visble!).
```sh
sudo rm -r /Applications/R.app
```
3. To delete the whole framework running behind R copy (&#8984;C) the following line, paste (&#8984;V) it behind the console prompt in the terminal and press return (&#8617;) to execute. No password will be asked anymore, as long as you do not close the terminal application.
```sh
sudo rm -r /Library/Frameworks/R.framework
```
4. To be able to re-install R the installation receipts need to be removed. This is done by copying (&#8984;C) the following lines (including the *) one by one, pasting (&#8984;V) them behind the prompt in the terminal and pressing return (&#8617;) to execute.
```sh
sudo rm -r /private/var/db/receipts/org.r-project.*
```
```sh
sudo rm -r /private/var/db/receipts/org.R-project.*
```
5. Delete R application support by copying (&#8984;C) the following line, pasting (&#8984;V) it behind the prompt in the terminal and pressing return (&#8617;) to execute.
```sh
sudo rm -r ~/Library/Application Support/R
```
6. Clean the cache of R by copying (&#8984;C) the following line, pasting (&#8984;V) it behind the prompt in the terminal and pressing return (&#8617;) to execute.
```sh
sudo rm -r ~/Library/Caches/org.R-project.org
```
7. To remove R preferences copy (&#8984;C) the following line, paste (&#8984;V) it behind the prompt in the terminal and press return (&#8617;) to execute.
```sh
sudo rm ~/Library/Preferences/org.R-project.org.plist
```
8. Deletion of all previously installed user packages is achieved by copying (&#8984;C) the following line, pasting (&#8984;V) it behind the prompt in the terminal and pressing return (&#8617;) to execute. A notification will be given in case the folder does not exist.
```sh
sudo rm -r ~/Library/R
```
9. Delete user created environment variables, used at startup of R, copy (&#8984;C) the following line, paste (&#8984;V) it behind the prompt in the terminal and press return (&#8617;) to execute. A notification will be given in case the file does not exist.
```sh
sudo rm  ~/.Renviron
```
10. Finally delete the user folder with additional settings by copying (&#8984;C) the following line, pasting (&#8984;V) it behind the prompt in the terminal and pressing return (&#8617;) to execute. A notification will be given in case the folder does not exist.
```sh
sudo rm -r ~/.R
```
{{% callout note %}}
Having performed all 10 steps given above, your mac will be ready for a new installation of R. Leave the terminal console open for now, you might need it later on.
{{% /callout %}}

## Download 
At the time this post was written, the latest release of R was version 3.6.3. It has been updated to the latest release version 4.2.2 of R (nicknamed: "Innocent and Trusting"") for macOS High Sierra or higher.

For newer versions of R than 3.6.3 the steps described below are the same and still correct, but start with a newer version of the downloaded package file of R. The screenshots in this post have not been updated. Therefore, what you see during your installation can (and probably will) differ with respect to the version number shown in the screenshots.

{{% callout warning %}}
For macOS there are three downloads for R available on the [R-project website](https://cloud.r-project.org/). To see which version of macOS is installed on your mac, click on {{< icon name="apple" pack="fab" >}} in the menu bar and select ‘About This Mac’.

__NOTE__: If you are using a mac with the newest M1 or M2 processor, download the __Apple Silicon arm64__ build!
{{% /callout %}}

Download R for your specific version of macOS using one of the following links:

- For macOS El Capitan (10.11.x) up to and including macOS Mojave (10.14.x): [{{< icon name="download" pack="fas" >}} R 3.6.3 (ca. 77 MB,  *regular* 64-bit)](https://cloud.r-project.org/bin/macosx/R-3.6.3.nn.pkg)
- For macOS High Sierra (10.13.x) and higher (__Intel 64-bit__ build): [{{< icon name="download" pack="fas" >}} R 4.2.2  (ca. 87MB, *notarized and signed* __Intel 64-bit__ build)](https://cloud.r-project.org/bin/macosx/base/R-4.2.2.pkg)
- For macOS Big Sur (11.x) and higher (__Apple silicon arm64__ build for M1 or M2 processor MACS only): [{{< icon name="download" pack="fas" >}} R 4.2.2  (ca. 87 MB, *notarized and signed* __ARM 64-bit__ build)](https://cloud.r-project.org/bin/macosx/big-sur-arm64/base/R-4.2.2-arm64.pkg) <!--Due to an error in the release for the Apple silicon arm64 build, use the above download for the Intel 64-bit version!-->

## Installation
For installing R on macOS follow these steps:

1. Open the downloaded file, either **R-3.6.3.nn.pkg**, **R-4.2.2.pkg** or **R-4.2.2-arm64.pkg**  depending or your version of macOS or processor (as explained above). This file will most likely reside in Finder > Downloads (shortcut: &#8997;&#8984;L). The file can more easily be found by switching into List view (shortcut: &#8984;2). To switch to Icon view use the shortcut: &#8984;1. The installer package will resemble the image displayed below in [Figure 3](#figure-icon_r_package) (text underneath can, and probably will, differ!).

{{< figure src="r-macos/1-r-installer-package-icon.png" caption="Icon R Installer Package." numbered="true" id="icon_r_package" >}}

2. The installler will start and display the introduction as shown below in [Figure 4](#figure-r_install_intro). Click the ‘Continue’ button to proceed.

{{< figure src="r-macos/2-r-installer-intro.png" caption="R Installer Introduction." numbered="true" id="r_install_intro" >}}

3. Now the Read Me for the software to be installed as displayed in [Figure 5](#figure-r_install_readme) below. Click the ‘Continue’ button to proceed.

{{< figure src="r-macos/3-r-installer-read-me.png" caption="R Installer Read Me." numbered="true" id="r_install_readme" >}}

4. Right after the Read Me a Software Licence Agreement will appear. By clicking the ‘Continue’ button you will be asked to agree with this software licence agreement as diplayed below in [Figure 6](#figure-r_install_agreed). Click on ‘Agree’ to proceed.

{{< figure src="r-macos/5-r-installer-license-agree.png" caption="R Installer License Agreement." numbered="true" id="r_install_agreed" >}}

5. The installer will select the best destination to install the software for you and will display the Installation Type as shown in [Figure 7](#figure-r_install_type). Click on the ‘Install’ button to start the software installation.

{{% callout warning %}}
Do not Customise the installation type, unless you know what you are doing.
{{% /callout %}}

{{< figure src="r-macos/6-r-installer-install-type.png" caption="R Installer Installation Type." numbered="true" id="r_install_type" >}}

6. Before the software installation will commence, confirmation of the user is requested as displayed below in [Figure 8](#figure-r_install_confirm). Either use the finger print scanner on the touch bar of your mac or confirm using the password of your mac.

{{< figure src="r-macos/7-r-installer-confirm-install.png" caption="Confirm R Software Installation." numbered="true" id="r_install_confirm" >}}

7. The software installer will start installing R onto your mac. When completed the installer will show a summary stating that the installation was successful as shown in [Figure 9](#figure-r_install_success) below. Click on the ‘Close’ button.

{{< figure src="r-macos/8-r-installer-success.png" caption="R Software Installation Success." numbered="true" id="r_install_success" >}}

8. The installer will finally ask you whether you want to keep or move to R installer package to the trashbin. Click ‘Move to Bin’ to discard the installer package.

{{% callout note %}}
Congratulations :satisfied:, you now have R 3.6.3 or higher installed on your mac! Before actively using the R application, some configuration will be required. The configuration is described in the next section.
{{% /callout %}}

## Configure the R application on macOS
To configure the R application on macOS perform the following steps:

1. Start the R application from Finder > Applications (shortcut: &#8679;&#8984;A) or via Launchpad. The icon representing the R application is shown below in [Figure 10](#figure-r_app_icon).

{{< figure src="r-macos/1-r-app-icon.png" caption="R Application Icon." numbered="true" id="r_install_success" >}}

2. The R Console will open, as shown in [Figure 11](#figure-r_app_console) below, and the cursor will be ready for input behind the prompt, indicated by the `>` sign. In case the R Console displays a non-UTF8 locale warning, than this needs to be remedied first. Go to the section entitled [Fix R application non-UTF8 locale warning](#fix-r-application-non-utf8-locale-warning) in this post to resolve this issue.

{{< figure src="r-macos/4-r-app-console.png" caption="R Application Console." numbered="true" id="r_app_console" >}}

3. Navigate the mouse pointer to the menu bar click on ‘R’ > ‘Preferences...’ (shortcut: &#8984;,) to open the R application preferences. The Preferences window displayed in [Figure 12](#figure-r_app_preferences) will appear.

{{< figure src="r-macos/5-r-app-preferences.png" caption="R Application Preferences." numbered="true" id="r_app_preferences" >}}

4. Click on Startup. The Preferences window will change into what is shown in [Figure 13](#figure-r_app_startup).

{{< figure src="r-macos/6-r-app-prefs-startup.png" caption="R Application Startup Preferences." numbered="true" id="r_app_startup" >}}

5. Match the Startup settings displayed above in [Figure 13](#figure-r_app_startup). To select the Default CRAN mirror click on the ‘Select’ button. The window shown below in [Figure 14](#figure-r_select_cran_mirror) will appear. Select ‘0-Cloud [https]’ and click ‘OK’ to confirm.  Having matched the settings, close the window using the red ball in the top left corner of the Startup window.

{{< figure src="r-macos/7-r-app-prefs-startup-default-cran.png" caption="R Application Startup Preferences CRAN Mirror Selection." numbered="true" id="r_select_cran_mirror" >}}

6. Quit the R application either by:
    * Typing `q()` or `quit()` behind the R Console prompt (indicated by the `>` sign) and pressing return (&#8617;) to execute.
    * Using the keyboard shortcut: &#8984;Q
    * Navigating the mouse pointer to the menu bar and clicking ‘R’ > ‘Quit R’
    * Navigation the mouse pointer to the top left corner of the R Console window and clicking on the red ball

7. No matter what you choose, you will always be asked whether you want to save a workspace image as shown below in [Figure 15](#figure-r_app_save_workspace). Just click on the **‘Don't Save’** button to end the R application.

{{< figure src="r-macos/3-r-app-save-workspace.png" caption="R Application Save Workspace." numbered="true" id="r_app_save_workspace" >}}

{{% callout note %}}
Having configured the R application, you are now ready to actively start using it!
{{% /callout %}}

## Fix R application non-UTF8 locale warning

When the R Console displays a non-UTF8 locale warning at the startup of the R application, it will look like the image shown below in [Figure 16](#figure-r_app_language_warning).

{{< figure src="r-macos/2-r-app-language-warning.png" caption="R Application Console with Language Warning." numbered="true" id="r_app_language_warning" >}}

The remedy for this issue is not difficult, just perform the following steps:

1. Go to the open terminal console. If you do not have one yet, open the Terminal application from Finder > Applications > Utilities (shorcut: &#8679;&#8984;U) or via Lauchpad under the ‘Other’ group. The terminal console prompt, where the commands will be entered, is depicted by a `%` or a `$` sign. Which sign is shown, depends whether your default shell is zsh (`%` sign) or bash (`$` sign).
2. Copy (&#8984;C) the following line, paste (&#8984;V) it behind the prompt in the terminal console and press return (&#8617;) to execute the command.
```sh
defaults write org.R-project.R force.LANG en_US.UTF-8
```
3. Quit the active terminal console by typing `exit` and pressing return (&#8617;) to execute. To quit the Terminal application completely you can use the keyboard shortcut: &#8984;Q or navigate the mouse pointer to the menu bar and click ‘Terminal’ > ‘Quit Terminal’.
4. Go back to the R Console and quit the R application either by:
    * Typing `q()` or `quit()` behind the R Console prompt (indicated by the `>` sign) and pressing return (&#8617;) to execute.
    * Using the keyboard shortcut: &#8984;Q
    * Navigating the mouse pointer to the menu bar and clicking ‘R’ > ‘Quit R’
    * Navigation the mouse pointer to the top left corner of the R Console window and clicking on the red ball
5. No matter what you choose, you will always be asked whether you want to save a workspace image as shown in [Figure 17](#figure-r_app_save_workspace2) below. Just click on the **‘Don't Save’** button to end the R application.

{{< figure src="r-macos/3-r-app-save-workspace.png" caption="R Application Save Workspace." numbered="true" id="r_app_save_workspace2" >}}

6. Go back to step 1. of the [Configure the R application on macOS](#configure-the-r-application-on-macos) section.
