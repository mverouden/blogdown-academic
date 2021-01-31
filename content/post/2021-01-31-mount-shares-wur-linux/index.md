---
title: Mounting WUR shares in Linux
summary: Instructions on how to mount WUR shares in Linux.
authors:
- admin
date: '2021-01-31'
slug: mount-shares-wur-linux
categories:
  - WUR
  - Linux
tags:
  - WUR
  - Shares
  - Linux
lastmod: '2021-01-31T14:00:00+01:00'
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
At Wageningen University & Research Linux as Operating System is supported on a best effort principle, meaning that it is supported as far as the knowledge of Facilities and Services Information Technology (FB-IT) reaches. FB-IT is supported by their colleagues maintaining the High Performance Computing Cluster Anunna, who have a lot of knowledge about the Linux Operating System because Anunna uses it. <!-- and there is a support mail address: <a href="mailto:linux.beheer@wur.nl">linux.beheer AT wur.nl</a>, where support questions can be sent.-->

On the other hand Linux users are generally users, who are very independent and know how to search for and implement solutions themselves. Being one of those Linux users within WUR myself, I want to share how I mount shares within Wageningen University & Research.

{{% callout note %}}
This post will show how to mount shares on a desk- or laptop using Linux as Operating System within WUR.
{{% /callout %}}

{{% callout warning %}}
To be able to mount WUR shares in the network the desktop or laptop needs to be in the wurnet, either physically or via a VPN connection. For setting up a VPN connection with  the wurnet, see the [Setting up VPN]()
{{% /callout %}}
