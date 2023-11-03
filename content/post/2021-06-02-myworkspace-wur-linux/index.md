---
## The title of your page (Core)
title: "Install and configure MyWorkSpace at WUR in Linux"
## An optional subtitle that will be displayed under the title
subtitle: ''

## Add the short URL slug containing keywords
slug: myworkspace-wur-linux

## A one-sentence summary of the content on your page. 
##   The summary can be shown on the homepage and can also benefit your search
##   engine ranking.
summary: Instructions how to install and configure MyWorkSpace at WUR in Linux.

## Display the authors of the page and link to their user profiles if they exist.
authors:
  - admin

## Tagging your content helps users to discover similar content on your site. 
##   Tags can improve search relevancy and are displayed after the page content
##   and also in the Tag Cloud widget.
tags:
  - WUR
  - Installation
  - MyWorkspace
  - Linux

## Categorizing your content helps users to discover similar site content.
##   Categories can improve search relevancy and display at the top of a page
##   alongside a page’s metadata.
categories:
  - WUR
  - Linux

## The RFC 3339 date that the page was published. 
date: '2021-06-02'
##   Dates can now be hidden from pages by adding show_date: false in page front
##   matter or by automatically applying it to all pages in a collection using
##   Hugo's cascade:>show_date: false in the _index.md file.
show_date: true

## The RFC 3339 date that the page was published. 
##   You only need to specify this option if you wish to set date  in the future
##   but publish the page now, as is the case for publishing a journal article
##   that is to appear in a journal, etc.
# publishDate: '2020-11-03T00:00:00Z'

## The RFC 3339 date that the page was last modified. 
##   If using Git, enable enableGitInfo in `config.yaml` to have  the page
##   modification date automatically updated, rather than manually specifying
##   lastmod.
lastmod: '2022-05-31T16:14:00+02:00'

## By setting `featured: true`, a page can be displayed in the Featured widget. 
##   This is useful for sticky, announcement blog posts or selected publications,
##   etc.
featured: false

## By setting `draft: true`, only you will see your page  when you preview your
## site locally on your computer.
draft: false

## Featured image
##   To use, add an image named `featured.jpg/png` to your page's folder.
##   Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
##   Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right,
##   BottomLeft, Bottom, BottomRight
image:
  # placement: 2
  caption: 'Image credit: [**_Unknown_ on Google**](https://www.google.com/)'
  focal_point: "Center"
  preview_only: false
  # alt_text: An optional description of the image for screen readers.

## Projects
##   Associate this post with one or more of your projects.
##   Simply enter your project's folder or file name without extension.
##   E.g. `projects = ["internal-project"]` references
##   `content/project/internal-project/index.md`.
##   Otherwise, set `projects = []`.
projects: []

## Page resources
##   Buttons can be generated in the page header to link to associated resources.
##   The example below shows how to create a Twitter link for a project and 
##   how to create a link to a post that was originally published on Medium:
# links:
#   - icon: twitter
#     icon_pack: fab
#     name: Follow
#     url: 'https://twitter.com/Herb_hewang'
#   # - icon_pack: fab
#   #   icon: medium
#   #   name: Originally published on Medium
#   #   url: 'https://medium.com'   # (required)

## The following parameters can be added to the front matter of 
##   a page (such as a blog post) to control its features:
##
## Show estimated reading time?
reading_time: true
## Show social sharing links?
share: true
## Show author profile?
profile: true
## Allow visitors to comment?
## Supported by the Page, Post, and Docs content types.
commentable: false
## Allow visitors to edit the page?
## Supported by the Page, Post, and Docs content types.
editable: false

## To enable LaTeX math rendering for a page, you should include `math: true` in
## the page’s front matter.
##   Not necessary if globally enabled `math.enable: true` in
##   `config/_default/params.yaml`
math: false

## Enable a Markdown extension for diagrams by toggling the diagram 
##   option in your `config/_default/params.toml` file or by adding
##   `diagram: true` to your page front matter.
diagram: false

## Image gallery:
## To add an image gallery to a page bundle
# Discarded for any remote gallery images see: https://wowchemy.com/blog/v5.1.0/#apply-breaking-changes
# gallery_item:
#   - album: 'branch-bundle-1'
#     image: 'GW150914Anniversary.png'
#     caption: 'Write your image caption here'  # only shown when zoom out
#     order: "asc" # "asc" or "desc"
#     resize_options:  # which supports Hugo image processing options.
#   # - album: gallery        # can not be replaced
#   #   image: 'sketch5.png'  # `static/media/sketch5.png`
#   #   caption: A caption    # only shown when zoom out
#   # - album: gallery
#   #   image: https://vip1.loli.net/2020/11/11/OmVGhaz79iQJsvj.png
#   #   caption: Another caption  # only shown when zoom out

## (Optional) Header image (relative to `assets/media/` folder).
##   To display a full width header image, the header parameters below can be 
##   inserted towards the end of a page’s front matter. It is assumed that the 
##   image is located in your `assets/media/` media library
# header:  # (It not works.....)
#   image: "header.png"
#   caption: "Image credit: [**MLflow**](https://mlflow.org)"
---

{{% toc %}}

## Motivation
At Wageningen University & Research the Linux Operating System is supported on a best effort principle, meaning that it is supported as far as the knowledge of Facilities and Services Information Technology (FB-IT) reaches. FB-IT is supported by their colleagues maintaining the High Performance Computing Cluster Anunna, who have a lot of knowledge about the Linux Operating System, because it's the Operating System used by Anunna. <!-- and there is a support mail address: <a href="mailto:linux.beheer@wur.nl">linux.beheer AT wur.nl</a>, where support questions can be sent.-->

Unfortunately not all programs are available for the Linux Operating System, that employees need for their work at Wageningen University & Research. One example is MyProjects, which employees need for time recording of their workweek. This program is only available on Windows WURclients. Therefore, it is essential to be able to access a Windows WURclient when needed.

One solution would be to use a remote desktop client to access a Windows WURclient desktop. However, this would require each Linux user to have access to at least one Windows WURclient desktop. A more elegant solution is to use a Virtual Windows WURclient desktop via MyWorkspace.

In this post I will describe, how to install and configure MyWorkspace at Wageningen University & Research on a Debian/Ubuntu based Linux system.

{{% callout note %}}
This post will show how to install and configure MyWorkspace on a Debian/Ubuntu based Linux system within WUR.
{{% /callout %}}

{{% callout warning %}}
Connecting to a Virtual Windows WURclient desktop with VMWare Horizon Client __does not require__ a VPN connection. 

VMWare Horizon Client has ssh-tunneling build into the application and, therefore, creates its own safe connection to WURNET.
{{% /callout %}}

## Download VMWare Horizon Client
At the time this post was written Horizon 8 is the latest version of the VMWare Horizon client. To check if there is a newer version available, check the pull down menu in the top left of the web page provided below.

To download the latest version of VMWare Horizon Client perform the following steps:

1. Open in a web browser [https://my.vmware.com/en/web/vmware/downloads/info/slug/desktop_end_user_computing/vmware_horizon_clients/horizon_8](https://my.vmware.com/en/web/vmware/downloads/info/slug/desktop_end_user_computing/vmware_horizon_clients/horizon_8)
2. Navigate to '__VMware Horizon Client for 64-bit Linux__' and click the '__GO TO DOWNLOADS__' link provided on that line.
3. A new page will open in the same window. Select the version to download. At the time this post written the version of the VMware Horizon Client for 64-bit Linux was version 2013 build number: 17742757 (Release Date	2021-03-23). The post has been updated to the latest VMware Horizon Client for 64-bit Linux version 2309 build number: 22660930 (Release Date 2023-10-26).
4. Click on the __GO TO DOWNLOADS__ button behind "VMware Horizon Client bundle installer for 64-bit Linux".
5. Right-click the __DOWNLOAD NOW__ button and copy the link address.
6. Open a terminal
6. Change the directory to your personal downloads directory with the command `cd ~/Downloads/`
8. Execute the following command to download the VMWare Horizon Client bundle: `wget URL`. Instead of `URL` use the copied '__DOWNLOAD NOW__' url from step 4. This url can be pasted in the console with `Shift+Insert`. With the latest version, the command will look like this:
```sh
wget https://download3.vmware.com/software/CART24FQ3_LIN64_2309/VMware-Horizon-Client-2309-8.11.0-22660930.x64.bundle
```
9. After the download has finished, as administrator (root) make the downloaded bundle executable with `chmod +x` in the terminal, e.g.
```sh
sudo chmod +x VMware-Horizon-Client-2309-8.11.0-22660930.x64.bundle
```
10. Do not close the terminal!

## Install VMWare Horizon Client

In the following part it is assumed that you are using a Linux system, which is based on at least Ubuntu 19.04, for example Linux Mint 20, or higher. I assume that your Linux system is using `/usr` merge, where softlinks have been created between `/` folders and their equivalents in `/usr` (e.g. `/bin -> /usr/bin`, `/lib -> /usr/lib`, *etc.*).

To install VMWare Horizon Client perform the following steps:

1. Become root in the terminal using: `sudo -i`. Your console prompt should change to `root@<your-system-name>:~#`.
2. Change the active directory to `/usr/lib/x86_64-linux-gnu/` using:
```sh
cd /usr/lib/x86_64-linux-gnu/
```
3. Create the following softlinks:

    + `ln -sf libudev.so.1 libudev.so.0`
    + `ln -sf libgstapp-1.0.so.0 libgstapp-0.10.so.0`
    + `ln -sf libgstbase-1.0.so.0 libgstbase-0.10.so.0`
    + `ln -sf libgstreamer-1.0.so.0 libgstreamer-0.10.so.0`
    + `ln -sf libffi.so.7 libffi.so.5` (in Linux Mint 21 replace `libffi.so.7` by `libffi.so.8`)

4. Leave the adminstrator (root) mode in the terminal by executing: `exit`
5. Change the directory to your Downloads folder with `cd ~/Downloads`
6. Start the VMWare Horizon Client installer, for the version you downloaded, as administrator (root):
```sh
sudo ./VMware-Horizon-Client-2309-8.11.0-22660930.x64.bundle --eulas-agreed
```

7. Follow the steps of the installer to properly install VMWare Horizon Client. Make sure all boxes during the installation with respect to USB Redirection, Virtual Printing, *etc.* are ticked during the installation of the VMWare Horizon client to ensure correct operation later.

## Configure VMWare Horizon Client
Once the installation of the VMWare Horizon Client has finished, the application can be started (logging out and in might be required).

Next a connection server needs to be added to the client. The address to use is: `workspace.wur.nl`

To log in to MyWorkspace you need to provide:

* Username: `user001` (this is your WUR username)
* Password: `your-windows-password` (this is the WUR Windows password for your WUR username)
* Domain: `WUR` (this is optional, because the client will use the domain as provided by the connection server)

### VMWare Horizon Blast Settings 
After adding the connection server and logging in the VMWare Horizon Blast settings need to be configured. This has to done only once.

Navigate to and click '__File__' in the top menu of the VMWare Horizon Client. Next select '__Configure VMWare Blast__'. Match the setting as displayed in [Figure 1](#figure-config_vmware_blast) and click '__OK__' to confirm.

{{< figure src="myworkspace-linux/1-configure-vmware-blast.png" caption="Configure VMWare Horizon Blast" numbered="true" id="config_vmware_blast" >}}

{{% callout note %}}
Now VMWare Horizon Client is fully installed, configured and ready to log in to a Virtual Windows WURclient desktop, where you can use MyProjects and other Windows only applications you need to do your work within WUR. 
{{% /callout %}}

## Uninstall VMWare Horizon Client

To uninstall VMWare Horizon Client for Linux the installation bundle of the installed version is required. Check the installed version and see [Download VMWare Horizon Client](#download-vmware-horizon-client) on how to obtain and make it executable.

To uninstall VMWare Horizon Client for Linux issue the following command in a terminal:
```sh
sudo env VMWARE_KEEP_CONFIG=yes ./VMware-Horizon-Client-2309-8.11.0-22660930.x64.bundle -u vmware-horizon-client
```

{{% callout warning %}}
Do not forget to modify the command above to reflect the correct version you wish to uninstall!
{{% /callout %}}

This will retain the VMWare Horizon Client configuration setings on your system. In order to also remove the configuration settings set `VMWARE_KEEP_CONFIG=no`.
