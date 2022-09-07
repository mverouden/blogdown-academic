---
title: "R installation on Windows 10/11"
subtitle: ''

# Summary for listings and search engines
summary: Instructions on how to install R on Windows 10/11.

# Link this post with a project
projects: []

# Date published
date: '2020-04-06'

# Date updated
lastmod: '2022-05-29T23:43:13+02:00'

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
  - Windows 10
  - Windows 11

categories:
  - R
  - Windows 10
  - Windows 11
  - WUR

slug: r-installation-windows-10

share: true
---

{{% toc %}}

## Motivation
<!--Due to the novel coronavirus (SARS-CoV-2) and its related disease :mask: COVID-19 employees and students at Wageningen University & Research are all working from home.-->

Whether working or studying everybody uses various sorts and types of software on their computer. Students taking [Statistical Courses, as taught by the Mathematical and Statistical Methods group at Wageningen University & Research](https://www.wur.nl/en/Research-Results/Research-Institutes/plant-research/biometris/Education/BSc-and-Master-Courses.htm), will most likely use R.

{{% callout note %}}
This post will show how to install R on a **privately owned** desktop or laptop computer running Windows 10 or Windows 11 as operating system.
{{% /callout %}}

{{% callout warning %}}
The installation instructions in this post are <u>**not to be used on WURclient desktops or laptops**</u>! For a WURclient desktop or laptop see the post: [Custom R installation on a WURclient](/post/2021/01/24/r-installation-wurclient/).
{{% /callout %}}

Two ways to install R are offered here:

1. [WUR AppStore](#1-wur-appstore). This is the **RECOMMENDED** way, because it includes R and everything to run R Commander!
2. [Manual installation](#2-manual-installation) for those who, for whatever reason, do not want to use the WUR AppStore.

## 1. WUR AppStore
The WUR AppStore is the place where you will be able to download, link to, or virtually access the software you need for your study programme and courses. Not only during, but also for self-study after, the computer practical's and courses. 

For more information see: [What is the WUR AppStore](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1222947-what-is-the-wur-appstore)

### Windows 10/11 compatibility check and WUR AppStore installation

* First check if you have a compatible Windows 1011 version as described on: [How to check if you have the right Windows 10 version](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1198329-how-to-check-if-you-have-the-right-windows-10-version)
*  If you have Windows 10 Education or Windows 10 Pro (Professional), you can proceed to the manual: [How to get access to the WUR AppStore](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1203863-how-to-connect-to-the-wur-appstore).
* If you have another version of Windows 10/11 (e.g. Windows 10/11 Home), follow the manual: [How to get Windows 10 Education](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1223173-how-to-get-windows-10-education). After having upgraded Windows 10 to the Education version, you can proceed to the manual: [How to get access to the WUR AppStore](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1203863-how-to-connect-to-the-wur-appstore).

### Using the WUR AppStore
The use of the WUR AppStore is very well described by the WUR TEAM Study Anytime, Anyplace. The first article can be found here: [How can I use the WUR AppStore](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1203865-how-can-i-use-the-wur-appstore)

The WUR AppStore currently contains **R 4.2.1 Rcmdr**. **Rcmdr** indicates that, apart from running **R v4.2.1** by using the default Graphical User Interface (a.k.a. **RGUI**), everything is included to run **R Commander**.

### Support WUR AppStore
In case you need support installing or using the WUR AppStore you can contact the WUR Servicedesk IT either by telephone: <a href="tel:+31317488888">+31 (0)317 488888</a> / mail: <a href="mailto:Servicedesk.IT@wur.nl">Servicedesk.IT AT wur.nl</a>. You can also visit the Servicepoint IT, ground floor left of the Grand Café, in Forum (Building 102) on the WUR Campus.

## 2. Manual Installation

### Download
At the time this post was written, the latest release of R was version 3.6.3. It has been updated to the latest release version 4.2.1 of R, named "Funny-Looking Kid". As of version 4.2.0 the R software is only available as 64-bit, meaning that it will not install on a 32-bit version of Windows 10.

The installer for Windows 10/11 can be downloaded directly from this link: [{{< icon name="download" pack="fas" >}} R 4.2.1 for Windows (ca. 79 MB, 64-bit)](https://cloud.r-project.org/bin/windows/base/R-4.2.1-win.exe).

For newer versions of R than 3.6.3 the steps described below are the same and still correct, but start with a newer version of the downloaded executable file of R. The screenshots in this post have not been updated. Therefore, what you see during your installation will differ with respect to the version number shown in the screenshots.

### Installation

1. Open the downloaded file **R-4.2.1-win.exe**. This file will most likely reside in your Downloads folder of your user account.
2. Allow to install the software on your computer.
3. After the installer has started, a first selection window will appear as displayed below in [Figure 1](#figure-r_language). Select the English language and click the ‘OK’ button to proceed.

{{< figure src="r-windows/1-install-r-language.png" caption="Language Selection" numbered="true" id="r_language" >}}

4. Click on the ‘Next’ button to agree to the terms. After this a window will appear, allowing you to select or choose the destination folder, as shown in [Figure 2](#figure-r_destination_folder), where R version 4.2.1 for Windows should be installed. If you are content with the default `C:\Program Files\R\R-4.2.1` click on the ‘Next’ button to continu, otherwise use the ‘B<u>r</u>owse...’ button to navigate to an alternative destination or type the destination path directly into the text field displayed (currently showing `C:\Program Files\R\R-4.2.1`).

{{< figure src="r-windows/2-install-r-destination-folder.png" caption="Destination Location Selection" numbered="true" id="r_destination_folder" >}}

5. After selecting the installation destination folder the component selector will appear, as displayed in [Figure 3](#figure-r_components_selection). Most desktop and laptop computers these days are using a 64-bit architecture, therefore select (using the pull down menu) the 64-bit User installation as displayed in the image shown below and click on the ‘Next’ button.

{{< figure src="r-windows/3-install-r-select-components.png" caption="Selection Components to Install" numbered="true" id="r_components_selection" >}}

6. After selecting the components to install the startup options need to be set. Select, as shown in [Figure 4](#figure-r_customize_startup) below, the customized startup by selecting the ‘**Yes (customized startup)**’ radio button followed by clicking on the ‘Next’ button.

{{< figure src="r-windows/4-install-r-startup-options.png" caption="Customize Startup Options" numbered="true" id="r_customize_startup" >}}

7. The first startup option to set is the Display Mode, as shown below in [Figure 5](#figure-r_display_mode). Select the Single Document Interface by selecting the ‘**SDI (separate windows)**’ radio button as displayed and clicking on the ‘Next’ button.

{{< figure src="r-windows/5-install-r-display-mode.png" caption="Display Mode Selection" numbered="true" id="r_display_mode" >}}

8. Next select the help style startup option. Leave this at the default ‘**HTML help**’ value, as displayed in [Figure 6](#figure-r_help_style), and click on the ‘Next’ button.

{{< figure src="r-windows/6-install-r-help-style.png" caption="Help Style Selection" numbered="true" id="r_help_style" >}}

9. The one before last startup option is to set a ‘Start Menu’ folder name. Unless wishing to use a different name, leave the default value as displayed below in [Figure 7](#figure-r_start_menu). This will create a folder named ‘R’ in the ‘Start Menu’ of Windows, from which the R GUI (graphical user interface) can be started.

{{< figure src="r-windows/7-install-r-start-menu.png" caption="Start Menu Folder selection" numbered="true" id="r_start_menu" >}}

10. The last startup option to set allows for some customization of shortcut links. Preferably leave the default settings and continue by clicking on the ‘Next’ button. This will trigger the installation. At the end the image shown in [Figure 8](#figure-r_completion) will appear. To exit the setup click on the ‘Finish’ button.

{{% callout warning %}}
**Do not mess around with the ‘Registry entries’ settings.**
{{% /callout %}}

{{< figure src="r-windows/9-install-r-completion.png" caption="Completion of the R installation." numbered="true" id="r_completion" >}}

{{% callout note %}}
Congratulations, :satisfied:, you now have R version 4.2.1 installed on your private desktop or laptop computer!
{{% /callout %}}
