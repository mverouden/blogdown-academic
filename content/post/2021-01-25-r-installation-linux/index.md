---
title: R installation on Linux
summary: Instructions on how to install R on Linux.
authors:
- admin
date: '2021-01-25'
slug: r-installation-linux
categories:
  - R
  - Linux
tags:
  - Installation
  - R
  - Linux
lastmod: '2021-01-25T14:00:00+01:00'
draft: true
featured: false
image:
  caption: 'Image credit: [**_Unknown_ on Google**](https://www.google.com/)'
  focal_point: 'Center'
  preview_only: false
projects: []
---

{{% toc %}}

## Motivation
At Wageningen University & Research Linux is supported on a best effort principle, meaning that it is supported as far as the knowledge of Facilities and Services Information Technology (FB-IT) reaches. FB-IT is supported by the colleagues of High Performance Computing Cluster Anunna. <!-- and there is a support mail address: <a href="mailto:linux.beheer@wur.nl">linux.beheer AT wur.nl</a>, where support questions can be sent.-->

A WURclient desktop or laptop at Wageningen University & Research is not a standard Windows 10 computer. WURclients use Windows 10 Enterprise, which has been modified by Facilities and Services Information Technology (FB-IT) among others with respect to installation rights for security reasons.

WURclient desktops and laptops at Wageningen University & Research can install R from the Software Center created by the IT department, which is launched by clicking on Start and selecting the "Software Center" tile. At the time this post was written the latest version of R in Software Center is `R 4.0.2 Rcmdr`.

This version of R was developed for educational purposes, where `Rcmdr` reflects that the installer includes R Commander. Only once per year a new version of R (including R Commander and additional packages for serveral courses) is released in Software Center. The consequence is, that core packages can not be updated by users.

Many users, however, need to be able to update core packages, because of dependencies with packages they would like to install or would just like to use a newer version of R than the one in Software Center. At the moment of writing this post the latest version of R released on [r-project.org](https://www.r-project.org/) is R version 4.0.3 named: "Bunny-Wunnies Freak Out" (released on 2020-10-10).

{{% callout note %}}
This post will show how to custom install R on a **WURclient** desktop or laptop computer without using Software Center.
{{% /callout %}}

{{% callout warning %}}
The installation instructions in this post are <u>**not to be used on privately owned desktops or laptops**</u>! For a privately owned desktop or laptop see the post: [R installation on Windows 10](/post/2020/04/06/r-installation-windows-10/).
{{% /callout %}}

