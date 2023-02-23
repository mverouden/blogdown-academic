---
## The title of your page
title: 'Printing within WUR on Linux'
## An optional subtitle that will be displayed under the title 
subtitle: ''

## A one-sentence summary of the content on your page. 
##   The summary can be shown on the homepage and can also benefit your search
##   engine ranking.
summary: Instructions how to set up printing within WUR on Linux.

## Add the short URL slug containing keywords
slug: printing-wur-linux

## Display the authors of the page and link to their user profiles if they exist.
authors:
- admin

## Tagging your content helps users to discover similar content on your site. 
##   Tags can improve search relevancy and are displayed after the page content
##   and also in the Tag Cloud widget.
tags:
  - WUR
  - Printing
  - Linux

##   Categories can improve search relevancy and display at the top of a page
##   alongside a page’s metadata.
categories:
  - WUR
  - Linux

## The RFC 3339 date that the page was published. 
date: '2022-06-11T16:46:11+0200'
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
lastmod: '2022-06-11T17:00:00+0200'

## Cacommentable: false
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
  # placement: 1
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
At Wageningen University & Research the Linux Operating System is supported on a best effort principle, meaning that it is supported as far as the knowledge of Facilities and Services Information Technology (FB-IT) reaches. FB-IT is supported by their colleagues maintaining the High Performance Computing Cluster Anunna, who have a lot of knowledge about the Linux Operating System, because it's the Operating System used by Anunna. <!-- and there is a support mail address: <a href="mailto:linux.beheer@wur.nl">linux.beheer AT wur.nl</a>, where support questions can be sent.-->

On the other hand Linux users are generally users, who are very independent and know how to search for and implement solutions themselves. Being one of those Linux users within WUR myself I want to share in this post, how I have set up printing on my Linux systems to use the facilities offered at  Wageningen University & Research.

{{% callout note %}}
This post will show how to set up printing on a desk- or laptop using Linux as Operating System within WUR.

The described procedure should work on Ubuntu/Debian based Linux Operating Systems.
{{% /callout %}}

{{% callout warning %}}
To be able to print on facilities (multifunctionals) at WUR the desktop or laptop needs to be within WURNET, either physically or via a VPN connection. <!--For setting up a VPN connection with WURNET, see the post [to be added]().-->
{{% /callout %}}

## Download

For convenience the PostScript Printer Description (PPD) files of the printers in use at Wageningen University & Research are provided. You can save the files into the Downloads folder of your Linux desk- or laptop by right-clicking the link and selecting the option 'Save link as...' (**<span style="color:red">IMPORTANT:</span> <u>DO NOT CHANGE THE FILE NAMES!</u>**):

* {{< staticref "files/linux/print/Ricoh-IM_C4500-PDF-Ricoh.ppd" "newtab" >}}{{< icon name="download" pack="fas" >}} Ricoh-IM_C4500-PDF-Ricoh.ppd{{< /staticref >}}
* {{< staticref "files/linux/print/Ricoh-IM_C4500-Postscript-Ricoh.ppd" "newtab" >}}{{< icon name="download" pack="fas" >}} Ricoh-IM_C4500-Postscript-Ricoh.ppd{{< /staticref >}}

**<span style="color:red">RECOMMENDATION:</span> Use the Postscript PPD file for the Ricoh IM C4500. The other one (PDF ppd file) is provided just in case you require it.**

The Ricoh IM C4500 is since February 2023 the default printer at WUR. <!-- This specific driver also works perfectly with the Ricoh MP C4503 printers, that are more commonly used in WUR buildings.-->

## Printer Setup

1. Open the system printer configuration tool (alternatively use console command: `system-config-printer` in a terminal) as displayed below in [Figure 1](#figure-system-config-printer).

{{< figure src="printing-linux/1-system-printer-configuration.png" caption="System configuration for printers." numbered="true" id="system-config-printer" >}}

2. Click the ‘+ Add’ button to configure a new printing device and a window will open as shown in [Figure 2](#figure-add-new-printer).

{{< figure src="printing-linux/2-new-printer.png" caption="Configure a new printing device." numbered="true" id="add-new-printer" >}}

3. In the left column named **Devices** select ‘Network Printer’ > ‘Windows Printer via SAMBA’. As shown in [Figure 2](#figure-add-new-printer) fill the field **SMB Printer** with the address `smb://scomp5170/WURprinter` (printer queue, which handles printjobs at WUR).

4. Set the authentication details, as shown in [Figure 2](#figure-add-new-printer). Click the ‘Forward’ button to start the search for the printer driver as displayed below in [Figure 3](#figure-search-printer-driver)

{{% callout warning %}}
Username should start as displayed with `wur\` and replace `user001` with your personal WUR username. The Password provided should be the WUR Windows password for your WUR username. 
{{% /callout %}}

{{< figure src="printing-linux/3-searching-driver.png" caption="Searching for printer driver." numbered="true" id="search-printer-driver" >}}

5. The searching for drivers will take a little while, but none will be found. Instead a window will be presented as shown below in [Figure 4](#figure-choose-driver) to choose the proper printer driver. Use the radio button to select ‘Provide PPD file’ and select, as advised, the `Ricoh-IM_C4500-Postscript-Ricoh.ppd` file (see [Download](#download) section). Next click the ‘Forward’ button to continue.

{{< figure src="printing-linux/4-choose-driver.png" caption="Choose the printer driver." numbered="true" id="choose-driver" >}}

6. A window with **Installable Options** for the new printing device will open as shown in [Figure 5](#figure-installable-options). Select the settings shown and, afterwards, click the ‘Forward’ button to continue:
    + Option Tray: Lower Paper Trays **<span style="color:red">(SELECT THE PLURAL FORM HERE!)</span>**
    + Large capacity tray: Not Installed
    + Internal Tray 2: Installed
    + Internal Shift Tray: Not Installed
    + External Tray : Not Installed
    + Finisher: Finisher SR3250
    + Folding Unit: Not Installed
    + PostScript: PostScript Emulation

{{< figure src="printing-linux/5-installable-options.png" caption="Configure installable options for the printer." numbered="true" id="installable-options" >}}

7. Next you will asked to describe the printer, as shown in [Figure 6](#figure-describe-printer). Fill the fields as shown in the figure or with you own information:
    + **Printer Name**: WURprinter
    + **Description**: WUR printer Ricoh IM C4500 Postscript
    + **Location**: Anywhere within WUR with user's wurcard!

{{< figure src="printing-linux/6-describe-printer.png" caption="Printer description." numbered="true" id="describe-printer" >}}

8. Finish the printer setup by clicking on the ‘Apply’ button. A test print window will appear, as shown in [Figure 7](#figure-print-test). Select whether you want to print a test page already or press the ‘Cancel’ button to ignore.

{{< figure src="printing-linux/7-print-test.png" caption="Print test page request." numbered="true" id="print-test" >}}

{{% callout warning %}}
**REMOVE SHARING OFF THE WURprinter!!**  
Sharing allows other users to print on your WUR account. However, you will have to print and collect the print jobs with your WUR card. This is of course very undesirable.

To prevent this behavior, right-click the **WURprinter** as displayed in [Figure 1](#figure-system-config-printer) and remove the tick-mark in front of **Shared**. This sub-menu, appearing with right-clicking the **WURprinters**,  has other nice features such as making the selected printer your default.
{{% /callout %}}

## Resetting your WUR Password for printing

Every 4 months you need to change the password of your WUR Account for obvious safety reasons.

This also means that you need to change your WUR password in the printer settings, when you have filled your password during the printer setup (see [Printer Setup](#printer-setup) step 2.).

The are two options:

* Delete the **WURprinter** and set up a new printer, as described in [Printer Setup](#printer-setup).
* Modify the `/etc/cups/printers.conf` file to match your changed WUR password:

    1. Open a terminal (CTR+ALT+T)
    2. Issue the following command to shut down the Common UNIX Printing System (CUPS daemon):
    ```sh
      sudo service cups stop
    ```
    3. Open the `/etc/cups/printers.conf` file as adminstrator in a text editor, e.g.
    ```sh
      sudo xed /etc/cups/printers.conf
    ```
    4. Modify the line:
    ```sh
      DeviceURI smb://wur%5Cuser001:password@scomp5170/WURprinter
    ```
    5. In this line `wur%5C` represents `wur\`, where the `\` is encoded as hexadecimal ASCII character (see [ASCII table](https://www.asciitable.com/)). `user001` will be displaying your own personal WUR username. The part between `:` and `@` represents your password, in which special characters are encoded as hexadecimal ASCII characters. Modify the password part to match you new password.
        + e.g. new password: qu!ck4L!9H+2 (very strong password), needs to be provided in `printers.conf` as qu%21ck4L%219H%2B2
    6. Save the modified `/etc/cups/printers.conf` file and exit the text editor
    7. Restart the CUPS daemon:
    ```sh
      sudo service cups start
    ```

{{% callout note %}}
Having reset your WUR account password, you should be able to print again.
{{% /callout %}}
