---
## The title of your page (Core)
title: Mounting Windows WUR shares in Linux
## An optional subtitle that will be displayed under the title
subtitle: ''

## Add the short URL slug containing keywords
slug: mount-shares-wur-linux

## A one-sentence summary of the content on your page. 
##   The summary can be shown on the homepage and can also benefit your search
##   engine ranking.
summary: Instructions on how to mount WUR shares in Linux.

## Display the authors of the page and link to their user profiles if they exist.
authors:
  - admin

## Tagging your content helps users to discover similar content on your site. 
##   Tags can improve search relevancy and are displayed after the page content
##   and also in the Tag Cloud widget.
tags:
  - WUR
  - Windows
  - Shares
  - Linux

## Categorizing your content helps users to discover similar site content.
##   Categories can improve search relevancy and display at the top of a page
##   alongside a page’s metadata.
categories:
  - WUR
  - Linux

## The RFC 3339 date that the page was published. 
date: '2021-05-31'
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
lastmod: '2022-05-31T15:57:00+02:00'

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
## Discarded for any remote gallery images see: https://wowchemy.com/blog/v5.1.0/#apply-breaking-changes
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

On the other hand Linux users are generally users, who are very independent and know how to search for and implement solutions themselves. Being one of those Linux users within WUR myself, I want to share in this post, how I mount Windows shares from Wageningen University & Research within my Linux systems.

{{% callout note %}}
This post will show how to mount Windows shares on a desk- or laptop using Linux as Operating System within WUR.
{{% /callout %}}

{{% callout warning %}}
To be able to mount WUR shares in the network the desktop or laptop needs to be within WURNET, either physically or via a VPN connection. <!--For setting up a VPN connection with WURNET, see the post [to be added]().-->
{{% /callout %}}

## Mounting WURNET shares
The method of mounting Windows shares from Wageningen University & Research, described in this post, uses the Common Internet File System (cifs) via the `/etc/fstab` file. This allows for automatic mounting of Windows shares during boot, when the computer is physically within WURNET.

A prerequisite for the described method is that the common internet file system utilities `cifs-utils` are available on your Linux system. When in doubt, open a terminal and execute, one by one, the following commands:
```sh
sudo apt update
sudo apt install cifs-utils
```

### Create a credentials file in your HOME directory
The procedure described, using the `/etc/fstab` file, requires a credentials file to store your WUR Windows username and password. This credentials files needs to be stored in the root of your HOME directory `/home/localusername`, where `localusername` is your username on the Linux system.

Open a terminal and change the directory with:
```sh
cd ~
```

Print the current directory with `pwd` and confirm that you are in `/home/localusername`, where `localusername` reflects the username on your Linux system.

Create a credentials file, e.g. `.smbpassword`, with the following command:
```sh
touch .smbpassword
```

Using your favorite editor, e.g. VIM, Emacs, nano or whatever editor your prefer, edit `.smbpassword` and add the following lines:
```sh
username=user001
password=your-windows-password
domain=WUR
```
Here `user001` is your WUR username and `your-windows-password` is the current WUR Windows password, which you would use to log into  a WURclient computer or log in to get your WUR e-mail using Outlook  Online ([https://outlook.office365.com](https://outlook.office365.com)).

### Create a mount point for the Windows share
For each Windows share you wish to mount during boot, you need to create a mount point.

For example I have created a mount point for my personal WUR Windows share (also known as the `M:-drive` within WUR) under `/mnt` as `wur-m`. Creation of such a mount point is achieved with the following command:
```sh
sudo mkdir /mnt/wur-m
```
### Add filesystems to `/etc/fstab`
The file `/etc/fstab` contains descriptive information about the filesystems the system can mount. The file is only read by programs, and not written; it is your duty as system administrator to properly create and maintain this file.

Each filesystem is described on a separate line. **Fields on each line are separated by tabs.** Lines starting with `#` are comments. Blank lines are ignored.

#### Retrieve user and group identifier
To properly mount a filesystem the values of the user (`uid`) and group (`gid`) identifiers are required. To retrieve the `uid` and `gid` values issue the following command in a terminal:
```sh
id localusername
```
Here `localusername` should be your username on the Linux system.

In most Linux systems the first user will have `uid=1000` and `gid=1000`. Do not assume these values are the same for your system, always check with before mentioned command!

#### Open `/etc/fstab` and add the filesystem
The file containing static information about the filesystems resides in `/etc` and, therefore, can only be edited by the system administrator, also known as root.

Open `/etc/fstab` with administrator (root) privileges in your favorite text editor, e.g. VIM, Emacs, nano or whatever editor you prefer. As an example here the command to open the `/etc/fstab` file with `xed`:
```sh
sudo xed /etc/fstab
```

Start on a new line below everything already present in the `/etc/fstab` file.

To add your Personal WUR Windows share add the following line:
```sh
# WUR Personal M-drive
//fs01mixedsmb.wurnet.nl/DBL-STANDARD_HOMEDIR$/user001 /mnt/wur-m cifs credentials=/home/localusername/.smbpassword,user,uid=uidvalue,gid=gidvalue 0 0
```

* Make sure that there are **tabs** between each element in the line of the `/etc/fstab` file
* Replace `user001` with your WUR username
* Replace `localusername` with your username on the Linux system
* Replace `uidvalue` and `gidvalue` with the values obtained from the `id` command as described above.

#### Retrieving the address of the filesystem to be mounted
The easiest way to retrieve the address of the WUR filesystem to be mounted is via File Explorer on a Windows WURclient. A Linux user can alternatively use VMWare Horizon client to log into a virtual Windows desktop. Perform the following steps:

1. Open File Explorer
2. Navigate in the left column to `dfs-root (\\wurnet.nl) (W:)`.
3. Locate the the folder you wish to mount as a filesystem in your Linux system, e.g. a project folder under `PROJECTS`.
4. Right-click the folder you wish to mount as a filesystem and open up the `Properties`.
5. Click the tab `DFS` and denote the path provided.

Convert the denoted path to be used in the `/etc/fstab` file:
1. Replace each `\` with a `/`
2. Replace underscore characters in the folder name by `\137` (octal ascii code)
3. Replace whitspace characters in the folder name by `\040` (octal ascii code)

__*Examples*__  

* `W:\PSG\_Data Exchange (PSG-wide)` becomes:
```sh
//fs01mixedsmb.wurnet.nl/DBL-STANDARD_PSG$/PSG~\137Data\040Exchange\040(PSG-wide)
```
* `W:\PSG\PSG Biometris` (also known as the Biometris `N:-drive`) becomes:
```sh
//fs01mixedsmb.wurnet.nl/DBL-STANDARD_PSG$/PSG~PSG\040Biometris
```
* `W:\PROJECTS\BiomDatasetsArchive` becomes
```sh
//fs02mixedsmb.wurnet.nl/TPE-STANDARD_PROJECTS$/PROJECTS~BiomEDatasetsArchive
```
* `W:\PROJECTS\Biom_ZeZhu` becomes
```sh
//fs02mixedsmb.wurnet.nl/TPE-STANDARD_PROJECTS$/PROJECTS~Biom\137ZeZhu
```

### Mount a share after boot or setting up a VPN connection
When after booting your system a Windows share is not automatically mounted or you have set up a VPN connection to WURNET and want to mount a WUR Windows share from your `/etc/fstab` file, this is done by issuing the following command:
```sh
# For example connect /mnt/wur-m after setting up a VPN connection
sudo mount /mnt/wur-m
```

To disconnect a WUR Windows share, for example prior to breaking of a VPN connection, issue the following command:
```sh
# For example disconnect /mnt/wur-m prior to breaking a VPN connection
sudo umount /mnt/wur-m
```
