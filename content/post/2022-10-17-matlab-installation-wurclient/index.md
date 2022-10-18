---
## The title of your page
title: 'Mathworks Matlab installation on a WURclient computer'
## An optional subtitle that will be displayed under the title 
subtitle: ''

## A one-sentence summary of the content on your page. 
##   The summary can be shown on the homepage and can also benefit your search
##   engine ranking.
summary: 'Instructions on how to install Matlab on a WURclient computer.'

## Add the short URL slug containing keywords
slug: matlab-installation-wurclient

## Display the authors of the page and link to their user profiles if they exist.
authors:
  - admin

## Tagging your content helps users to discover similar content on your site. 
##   Tags can improve search relevancy and are displayed after the page content
##   and also in the Tag Cloud widget.
tags:
  - Installation
  - Matlab
  - WURclient

##   Categories can improve search relevancy and display at the top of a page
##   alongside a page’s metadata.
categories:
  - Matlab
  - WUR
  - WURclient

## The RFC 3339 date that the page was published. 
date: '2022-10-17T11:00:00+0200'
##   Dates can now be hidden from pages by adding show_date: false in page front
##   matter or by automatically applying it to all pages in a collection using
##   Hugo's cascade:>show_date: false in the _index.md file.
show_date: true

## The RFC 3339 date that the page was published. 
##   You only need to specify this option if you wish to set date  in the future
##   but publish the page now, as is the case for publishing a journal article
##   that is to appear in a journal, etc.
# publishDate: '2022-10-17T00:00:00Z'

## The RFC 3339 date that the page was last modified. 
##   If using Git, enable enableGitInfo in `config.yaml` to have  the page
##   modification date automatically updated, rather than manually specifying
##   lastmod.
lastmod: '2022-10-17T11:15:45+0200'

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
  caption: 'Image credit: [**_Panos Sakalakis_ on Unsplash**](https://unsplash.com/photos/AwDVMJKMjlU)'
  focal_point: 'Center'
  # placement: 2
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
#   - icon_pack: fab
#     icon: medium
#     name: Originally published on Medium
#     url: 'https://medium.com'   # (required)

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
math: true

## Enable a Markdown extension for diagrams by toggling the diagram
##   option in your `config/_default/params.toml` file or by adding
##   `diagram: true` to your page front matter.
diagram: true
---

{{% toc %}}

## Motivation
A WURclient desktop or laptop at Wageningen University & Research is not a standard Windows 10 computer. WURclients use Windows 10 Enterprise, which has been modified by Facilities and Services Information Technology (FB-IT) among others with respect to installation rights for security reasons.

WURclient computers at Wageningen University & Research can install "Matworks<sup>&#174;</sup> Matlab" from the Software Center created by the IT department, which is launched by clicking on Start and selecting the "Software Center" tile. At the time this post was written the latest version of Matlab<sup>&#174;</sup> in Software Center is `MATLAB R2021b (for NON commercial use only)`.<!-- Currently the latest available version in Software Center is `MATLAB R2021b (for NON commercial use only)`. -->

{{% callout warning %}}
Please note **(for NON commercial use only)**!

The license for Matworks<sup>&#174;</sup> Matlab is an Academic and **not** a Commercial license. You are not allowed to used this software for commercial projects within Wageningen Research.
{{% /callout%}}

The Matlab<sup>&#174;</sup> version in Software Center for WURclient computers has two major drawbacks:

1. It is not always the latest version available. While writing this post the version in Sofware Center, as stated above, is `MATLAB R2021b (for NON commercial use only)`, whereas the latest version on the site of The Mathworks<sup>&#174;</sup> is `Matlab R2022b`.
2. It requires an internet connection to the WURNET to be able to check out a license, outside the campus a VPN connection will enable checkout of the license file.

In this post the installation procedure for Mathworks<sup>&#174;</sup> Matlab will be given step wise. Thereby, providing a way to install the latest version as well as install the software on a WURclient laptop without having to connect to WURNET to checkout a license.

{{% callout note %}}
This post will show how to install Matworks<sup>&#174;</sup> Matlab on a **WURclient** desktop or laptop computer, where the user possesses <u>**POWER USER RIGHTS**</u>.
{{% /callout %}}

## Prerequisite
To be able to install Matworks<sup>&#174;</sup> Matlab you need to have <u>**POWER USER RIGHTS**</u> on the WURclient desktop or laptop.

To see whether you possess these rights, right-click any icon (except Recycle Bin or WUR HELP) on the desktop. When the opened menu contains the option 'WUR - Run with administrative rights' (seventh or eighth from the top), it means you have power user rights on that particular desktop or laptop.

## Installation

1. If you do not have one already, create a folder named `MyPrograms` in your `C:\`-drive. All programs, you install yourself on your WUR Desktop or Laptop, should be installed into this folder (`C:\MyPrograms`). The folder can be created using File Explorer on your WURclient computer.

2. Open an internet browser (e.g. Microsoft Edge or Google Chrome) and navigate to the following web-address: [https://nl.mathworks.com/login?uri=%2Fmwaccount%2F](https://nl.mathworks.com/login?uri=%2Fmwaccount%2F)

3. Log in with your WUR e-mail address and Mathworks<sup>&#174;</sup> password. If you have never visited The Mathworks<sup>&#174;</sup> website before, then create a new account with your WUR e-mail address. Remember the password (it never changes, unless you change it yourself)!

4. Once logged in you need to select:
    + MATLAB (Designated Computer): The installation is restricted for use to a host ID that identifies a particular computer, but not a particular user. Any number of people can log in and use the software, but not simultaneously.
    + MATLAB (Individual):  You can install and run the software on multiple computers. Each installation is restricted for use by a particular computer and a particular user name. This is advised for WURclient computers (desk- or laptops) and privately owned desk- or laptop computers.

5. After choosing the license type you will be sent to the License Center page of Mathworks<sup>&#174;</sup>. On this specific page you find a "Download" button. Pressing it allows you to download the version of Matlab<sup>&#174;</sup> you want to install. Leave the browser open, you will need it again later during the installation.

6. Once the download has finished, navigate to your downloads folder. Start the installer with a right mouse click and select "WUR – Run with administrative rights" as shown below in [Figure 1](#figure-explorer_cmd_pusr) and **make sure you install into "C:\MyPrograms"**.

{{< figure src="matlab-wurclient/1-install-with-wur-admin-rights.png" caption="Run CMD with 'WUR administrative rights' from File Explorer." numbered="true" id="explorer_cmd_pusr" >}}

7. In the meantime, while Matlab<sup>&#174;</sup> is installing, navigate in your browser to the tab "Install and Activate" of the Mathworks<sup>&#174;</sup> License Center. In the right side of the screen under RELATED TASKS click the link "Activate to Retrieve License File".

8. If you have not yet activated a computer on a Designated Computer or Individual License, the screen as displayed below in [Figure 2](#figure-manually_activate_software) will be shown

{{< figure src="matlab-wurclient/2-Manually-Activate-Software.png" caption="Manually Activate Software on a Computer" numbered="true" id="manually_activate_software" >}}

9. If you have already activated a computer, click on the "Activate a Computer" button and the screen displayed above in [Figure 2](#figure-manually_activate_software) will appear.

10. Select the Release and Operating System. To find the Host ID open the command prompt and type "vol c:". The Volume Serial Number (looking something like "1234-ABCD") printed in the command prompt, needs to be entered as Host ID. Use the number of you Desktop/Laptop, preceded with an D for a Desktop or an L for a Laptop, as the Activation Label  (e.g. D0123456) and press continue. After a question, whether the software is installed (just mark "yes" and continue), the window shown below in [Figure 3](#figure-download_license) will appear.

{{< figure src="matlab-wurclient/3-dowload-license-file.png" caption="Next Steps to use the Matlab<sup>&#174;</sup> software" numbered="true" id="download_license" >}}

11. Select "Download License File". The file will be downloaded as `license.lic` into your downloads folder.

12. Once the Matlab<sup>&#174;</sup> installation has finished, copy the `license.lic` file into `C:\MyPrograms\MATLAB\RYYYYv\licenses`, where RYYYYv represents the version you installed e.g. R2019a. In case the folder `C:\MyPrograms\MATLAB\RYYYYv\licenses` does not exist yet, create it yourself.

13. On your computer start “Activate Matlab RYYYYv” with administrative rights to correctly implement the downloaded license. In the start menu navigate to the item, right click and select “more” > “Open file location”. In the new File Explorer right click on “Activate Matlab RYYYYv” and select "WUR – Run with administrative rights".

14. Now you should be able to start MATLAB from your start menu without problems!

{{% callout note %}}
Congratulations, :satisfied:, you now have Mathworks<sup>&#174;</sup> Matlab installed on your WURclient desktop or laptop computer!
{{% /callout %}}
