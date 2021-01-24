---
title: R installation on Windows 10
summary: Instructions on how to install R on Windows 10.
authors:
- admin
date: '2020-04-06'
slug: r-installation-windows-10
categories:
  - R
  - Windows 10
  - WUR
tags:
  - Installation
  - R
  - Windows 10
lastmod: '2020-08-27T15:30:35+02:00'
draft: false
featured: false
image:
  caption: 'Image credit: [**_Panos Sakalakis_ on Unsplash**](https://unsplash.com/photos/AwDVMJKMjlU)'
  focal_point: 'Center'
  preview_only: false
projects: []
---

{{% toc %}}

## Motivation
Due to the novel coronavirus (SARS-CoV-2) and its related disease :mask: COVID-19 employees and students at Wageningen University & Research are all working from home. Students taking [Statistical Courses taught by Mathematical and Statistical Methods at Wageningen University & Research](https://www.wur.nl/en/Research-Results/Research-Institutes/plant-research/biometris/Education/BSc-and-Master-Courses.htm) will most likely use R.

{{% callout note %}}
This post will show how to install R on a **privately owned** desktop or laptop computer running Windows 10 as operating system.
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

### Windows 10 compatibility check and WUR AppStore installation

* First check if you have a compatible Windows 10 version as described on: [How to check if you have the right Windows 10 version](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1198329-how-to-check-if-you-have-the-right-windows-10-version)
*  If you have Windows 10 Education or Windows 10 Pro (Professional), you can proceed to the manual: [How to get access to the WUR AppStore](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1203863-how-to-connect-to-the-wur-appstore).
* If you have another version of Windows 10 (e.g. Windows 10 Home), follow the manual: [How to get Windows 10 Education](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1223173-how-to-get-windows-10-education). After having upgraded Windows 10 to the Education version, you can proceed to the manual: [How to get access to the WUR AppStore](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1203863-how-to-connect-to-the-wur-appstore).

### Using the WUR AppStore
The use of the WUR AppStore is very well described by the WUR TEAM Study Anytime, Anyplace. The first article can be found here: [How can I use the WUR AppStore](https://wur-studentsupport.screenstepslive.com/m/WURAppStore/l/1203865-how-can-i-use-the-wur-appstore)

The WUR AppStore currently contains **R v4.0.2 Rcmdr**. **Rcmdr** indicates that, apart from running **R v4.0.2** by using the default Graphical User Interface (a.k.a. **RGui**), everything is included to run **R Commander**.

### Support WUR AppStore
In case you need support installing or using the WUR AppStore you can contact the WUR Servicedesk IT either by telephone: <a href="tel:+31317488888">+31 (0)317 488888</a> / mail: <a href="mailto:servicedesk.it@wur.nl">servicedesk.it AT wur.nl</a>. You can also visit the Servicepoint IT, ground floor left of the reception desk, in Forum (Building 102) on the WUR Campus.

## 2. Manual Installation

### Download
At the time this post was written the latest release of R is version 3.6.3. It has been updated to the latest release version 4.0.3 of R. 

The installer for Windows 10 can be downloaded directly from this link: [R 4.0.3 for Windows (ca. 85 MB, 32- & 64-bit)](https://cloud.r-project.org/bin/windows/base/old/4.0.3/R-4.0.3-win.exe).

For newer versions of R than 3.6.3 the steps described below are the same and still correct, but start with a newer version of the downloaded executable file of R. The screenshots in this post have not been updated, therefore what you see during your installation will differ with respect to the version number shown in the screenshots.

### Installation

1. Open the downloaded file **R-4.0.3-win.exe**. This file will most likely reside in your Downloads folder of your user account.
2. Allow to install the software on your computer.
3. After the installer has started, a first selection window will appear as displayed below. Select the English language and click the ‘OK’ button to proceed.

![Language selection during R installation.](1-install-r-language.png)

4. Click on the ‘Next’ button to agree to the terms. After this a window will appear, allowing you to select or choose the destination folder, as shown below, where R 4.0.3 for Windows should be installed. If you are content with the default `C:\Program Files\R\R-4.0.3` click on the ‘Next’ button to continu, otherwise use the ‘B<u>r</u>owse...’ button to navigate to an alternative destination or type the destination path directly into the text field displayed (currently showing `C:\Program Files\R\R-4.0.3`).

![Destination folder during R installation.](2-install-r-destination-folder.png)

5. After selecting the installation destination folder the component selector will appear, as displayed below. Most desktop and laptop computers these days are using a 64-bit architecture, therefore select (using the pull down menu) the 64-bit User installation as displayed in the image shown below and click on the ‘Next’ button.

![Component selection during R installation.](3-install-r-select-components.png)

6. After selecting the components to install the startup options need to be set. Select, as shown below, the customized startup by selecting the ‘Yes’ radio button followed by clicking on the ‘Next’ button.

![Customized startup selection during R installation.](4-install-r-startup-options.png)

7. The first startup option to set is the Display Mode, as show below. Select the Single Document Interface by selecting the ‘SDI (separate windows)’ radio button as displayed and clicking on the ‘Next’ button.

![Display mode selection during R installation.](5-install-r-display-mode.png)

8. Next select the help style startup option. Leave this at the default ‘HTML help’ value, as displayed below, and click on the ‘Next’ button.

![Help style selection during R installation.](6-install-r-help-style.png)

9. The one before last startup option is to set a ‘Start Menu’ folder name. Unless wishing to use a different name, leave the default value as displayed below. This will create a folder named ‘R’ in the ‘Start Menu’ of Windows, from which the R GUI (graphical user interface) can be started.

![Start menu folder selection during R installation.](7-install-r-start-menu.png)

10. The last startup option to set allows for some customization of shortcut links. Preferably leave the default settings and continue by clicking on the ‘Next’ button. This will trigger the installation. At the end the image shown below will appear. To exit the setup click on the ‘Finish’ button.

{{% callout warning %}}
**Do not mess around with the ‘Registry entries’  settings.**
{{% /callout %}}

![Completion of the R installation.](9-install-r-completion.png)

{{% callout note %}}
Congratulations, :satisfied:, you now have R 4.0.3 installed on your private desktop or laptop computer!
{{% /callout %}}
