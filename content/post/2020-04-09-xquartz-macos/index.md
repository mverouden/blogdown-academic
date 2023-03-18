---
title: "XQuartz installation on macOS"
subtitle: ''

# Summary for listings and search engines
summary: Instructions on how to install XQuartz on macOS.

# Link this post with a project
projects: []

# Date published
date: '2020-04-09'

# Date updated
lastmod: '2022-05-30T19:12:16+02:00'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: [**_Maxim Hopman_ on Unsplash**](https://unsplash.com/photos/Hin-rzhOdWs)'
  focal_point: 'Center'
  #placement: 2
  preview_only: false

authors:
  - admin

tags:
  - Installation
  - XQuartz
  - R Commander
  - R
  - macOS

categories:
  - R
  - macOS
  - WUR

slug: xquartz-installation-macos

share: true
---

{{% toc %}}

## Motivation
<!--Due to the novel coronavirus (SARS-CoV-2) and its related disease :mask: COVID-19 employees and students at Wageningen University & Research are all working from home.-->

Whether working or studying everybody uses various sorts and types of software on their computer. Students taking [Statistical Courses, as taught by the Mathematical and Statistical Methods group at Wageningen University & Research](https://www.wur.nl/en/Research-Results/Research-Institutes/plant-research/biometris/Education/BSc-and-Master-Courses.htm), will most likely use R. Students enrolled in [MAT-15303 Statistics 1](https://ssc.wur.nl/Handbook/Course/MAT-15303) and [MAT-15403 Statistics 2](https://ssc.wur.nl/Handbook/Course/MAT-15403) will use R Commander instead of basic R. Therefore, they will need to install R Commander.

R Commmander has been programmed in Tcl (Tool Command Language) and uses Tk as a graphical user interface toolkit. To be able to use R Commander correctly on macOS, software needs to installed that enables the use of Tcl/Tk. XQuartz is the only software on macOS, which enables the operating system to use Tcl/Tk.

{{% callout note %}}
This post will show how to install XQuartz on a desktop or laptop computer running macOS as operating system.
{{% /callout %}}

In the text some symbol combinations are used for shortcuts, the following table explains the meaning of these symbols in relation to specific keys on your keyboard. To use the shortcuts press the keyboard keys simultaneously, e.g. &#8679;&#8984;A means &#8679;+&#8984;+A.

|  Icon   | &nbsp; | Keyboard Meaning             | &nbsp;&nbsp; |  Icon   | &nbsp; | Keyboard Meaning               |
|:-------:|:------:|:-----------------------------|:------------:|:-------:|:------:|:-------------------------------|
| &#8984; | &nbsp; | command                      | &nbsp;&nbsp; | &#8682; | &nbsp; | caps lock                      |
| &#8997; | &nbsp; | option (or alt)              | &nbsp;&nbsp; | &#8617; | &nbsp; | carriage return (return/enter) |
| &#8963; | &nbsp; | control                      | &nbsp;&nbsp; | &#9003; | &nbsp; | delete/backspace               |
| fn      | &nbsp; | function                     | &nbsp;&nbsp; | &#8998; | &nbsp; | forward delete (fn + &#9003;)  |
| &#8679; | &nbsp; | shift (either left or right) | &nbsp;&nbsp; | &#9099; | &nbsp; | escape                         |

## Download
At the time this post was written the release of XQuartz was version 2.7.11. It will work on Mac OS X Snow Leopard (version 10.6.x) or later, up to and including OS X Mountain Lion (version 10.8.x).

Download XQuartz using the following link: [{{< icon name="download" pack="fas" >}} XQuartz v2.7.11 (ca. 75.9 MB)](https://github.com/XQuartz/XQuartz/releases/download/XQuartz-2.7.11/XQuartz-2.7.11.dmg)

The latest release of XQuartz, however, is version 2.8.5. This version should be used for OS X Mavericks (version 10.9.x) or later.<!--, up to and including macOS Monterey (version 12.x).-->

Download XQuartz using the following link: [{{< icon name="download" pack="fas" >}} XQuartz v2.8.5 (ca. 103MB)](https://github.com/XQuartz/XQuartz/releases/download/XQuartz-2.8.5/XQuartz-2.8.5.pkg)

{{% callout warning %}}
Make sure you download and install the correct version!

To see which version of macOS is installed on your mac, click on {{< icon name="apple" pack="fab" >}} in the menu bar and select ‘About This Mac’.
{{% /callout %}}

## XQuartz Installation
The icons and screenshots shown in this post are for XQuartz v2.7.11 and have not been updated to the latest version of XQuartz. The procedure described, however, is still the same, although the version number displayed below can be different depending on the version you are installing.

To install XQuartz on macOS perform the following steps:

1. Open the downloaded XQuartz disk image or package. This file will most likely reside in Finder > Downloads (shortcut: &#8997;&#8984;L). The file can more easily be found by switching into List view (shortcut: &#8984;2). To switch to Icon view use the shortcut: &#8984;1. The XQuartz disk image will look like the image displayed below in [Figure 1](#figure-xquartz_disk_image) (version number may differ!).

{{< figure src="xquartz-macos/1-xquartz-disk-image.png" caption="Icon XQuartz Disk Image." numbered="true" id="xquartz_disk_image" >}}

2. Opening the XQuartz disk image will cause a window labeled ‘XQuartz-2.7.11’ or ‘XQuartz-2.8.5’ to appear containing a XQuartz installer package. This package looks like the image shown in [Figure 2](#figure-xquartz_package), however the version number may be different. Double click the XQuartz installer package to open the installer.

{{< figure src="xquartz-macos/2-xquartz-package-icon.png" caption="Icon XQuartz Installer Package." numbered="true" id="xquartz_package" >}}

3. The installer for XQuartz will appear, showing the Introduction as displayed below in [Figure 3](#figure-xquartz_intro). Click the ‘Continue’ button to proceed.

{{< figure src="xquartz-macos/3-xquartz-intro.png" caption="XQuartz Installer Introduction." numbered="true" id="xquartz_intro" >}}

4. Next the Read Me will appear as shown in [Figure 4](#figure-xquartz_readme) below. Click the ‘Continue’ button to proceed.

{{< figure src="xquartz-macos/4-xquartz-read-me.png" caption="XQuartz Installer Read Me." numbered="true" id="xquartz_readme" >}}

5. Right after the Read Me a Software Licence Agreement will appear. By clicking the ‘Continue’ button you will be asked to agree with this software licence agreement as diplayed in [Figure 5](#figure-xquartz_agreed). Click on ‘Agree’ to proceed.

{{< figure src="xquartz-macos/6-xquartz-license-agree.png" caption="XQuartz Installer Licence Agreement." numbered="true" id="xquartz_agreed" >}}

6. The installer will select the best destination to install the software for you and will display the Installation Type as shown below in [Figure 6](#figure-xquartz_install_type). Click on the ‘Install’ button to start the software installation.

{{< figure src="xquartz-macos/7-xquartz-install-type.png" caption="XQuartz Installer Installation Type." numbered="true" id="xquartz_install_type" >}}

7. Before the software installation will commence, confirmation of the user is requested as displayed in [Figure 7](#figure-xquartz_install_confirm). Either use the finger print scanner on the touch bar of your mac or confirm using the password of your mac.

{{< figure src="xquartz-macos/8-xquartz-confirm-install.png" caption="XQuartz Installation Confirmation." numbered="true" id="xquartz_install_confirm" >}}

8. Most likely a security request will pop up from your operating system, requesting access to control system events as shown below in [Figure 8](#figure-xquartz_allow_access). Click on the on the ‘OK’ button to grant access.

{{< figure src="xquartz-macos/9-xquartz-allow-access.png" caption="XQuartz Installer Access Request." numbered="true" id="xquartz_allow_access" >}}

9. Now you will be warned that to make XQuartz your default X11 server, as shown in [Figure 9](#figure-xquartz_logout_warning) below, you will need to log out and again log into your system. Click on the on the ‘OK’ button to continue.

{{< figure src="xquartz-macos/10-xquartz-x11-message.png" caption="XQuartz Log Out Warning for Setting X11 as Default." numbered="true" id="xquartz_logout_warning" >}}

10. The software installer will start installing XQuartz onto your mac. When completed the installer will show a summary stating, that the installation was successful (see [Figure 10](#figure-xquartz_install_success)). Click on the ‘Close’ button.

{{< figure src="xquartz-macos/11-xquartz-install-success.png" caption="XQuartz Successfully Installed." numbered="true" id="xquartz_install_success" >}}

11. The installer will finally ask you, whether you want to keep or move the XQuartz installer package to the trashbin. Click ‘Move to Bin’ to discard the installer package and simultaneously close the XQuartz disk image. In reality the XQuartz disk image will be put into the trashbin from which it can still be recovered!

{{% callout note %}}
Congratulations, you now have XQuartz installed on your mac :satisfied:!
{{% /callout %}}

{{% callout warning %}}
As mentioned in step 9. you have to make XQuartz your default X11 server by logging out and again logging in on your mac. Do this by navigating your mouse pointer to the menu bar, click on {{< icon name="apple" pack="fab" >}} and select ‘Log Out \<username\>...’. Here \<username\> will display the name you selected, while setting up your mac for the first time. Log back in and XQuartz will now be your default X11 server.

The best way, to make sure that XQuartz is set as your default X11 server, is to completely **Shutdown and Restart your mac**!
{{% /callout %}}
