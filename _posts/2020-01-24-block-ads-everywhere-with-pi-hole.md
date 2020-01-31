---
layout: post
title: Block Ads everywhere with Pi-hole
subtitle: A DNS sinkhole that protects your devices from ads
tags:
  - Ads
  - AdBlock
  - DNS
  - Pi-Hole
category:
  - Web
image: /img/user_upload/Pi-hole_Logo.png
share-img: /img/homepage.png
author:
  - stan_girard
date: '2020-01-24'
---
[Pi-hole](https://pi-hole.net/) allows you to block all the ads without even installing an ad blocker on your device.  One of the main advantages of [Pi-hole](https://pi-hole.net/) is that you can use it anywhere you like (TVs, smartphones, etc.)

* **Easy to Install - Less than 10 minutes**
* **Content is blocked before reaching your device**
* **Open Source, therefore, free**
* **Very fast & Reliable**

## Installation

To install [Pi-hole](https://pi-hole.net/), you'll either need a [Raspbery-Pi 4/3](https://amzn.to/38InYI1) or a small server such as one on [DigitalOcean](https://m.do.co/c/f9dca2b1ecc8)

For simplicity, I'll show you how to install it on [DigitalOcean](https://m.do.co/c/f9dca2b1ecc8)

### DigitalOcean

If you already have an account, you can skip to step 2.

1. **Create an account on DigitalOcean** [here](https://m.do.co/c/f9dca2b1ecc8).
2. **Create a Droplet** ![digitalocean-create-droplet.png]({{site.baseurl}}/img/user_upload/digitalocean-create-droplet.png)     - Choose **Ubuntu** ![digitalocean-image.png]({{site.baseurl}}/img/user_upload/digitalocean-image.png)

   ```
   - Choose the **1GB/1CPU** Option
   ```

   ```
   - Choose the **location that best suits your needs**
   ```

   ![digitalocean-location.png]({{site.baseurl}}/img/user_upload/digitalocean-location.png)     - Add an **SSH Key for better protection** or use the One-time Password ![digitalocean-sshkeys.png]({{site.baseurl}}/img/user_upload/digitalocean-sshkeys.png)     - Create the droplet
       

The deployment of the drop should take less than 2 minutes.

Once the droplet has been deployed, look for its IP address.

Then just log to your Droplet {% highlight bash %}

# SSH to your droplet

ssh root@<ipaddress> {% endhighlight %}

### Install Pi-Hole on your freshly installed Ubuntu or [Raspbery-Pi 4/3](https://amzn.to/38InYI1)

* **Run**

{% highlight bash %}

# One line installer

 curl -sSL https://install.pi-hole.net | bash {% endhighlight %}

* **Accept everything** except if you want to customize(only if you know what you are doing) ![pihole-installer.png]({{site.baseurl}}/img/user_upload/pihole-installer.png)   
* **Save the admin password** ![pihole-end-password.png]({{site.baseurl}}/img/user_upload/pihole-end-password.png)

## Re-configure your router so that Pi-hole is the DNS Server for your network

Doing this will make sure that it has a minimal impact on your current network setup. Most routers are by default the DNS Server for clients of the network. By replacing the DNS server used by your router with Pi-Hole DNS Server, it means that all the devices on your network will use that DNS Server.

* Log into your router as an administrator
* Set the primary and secondary DNS server to the IP address of your Pi-Hole installation.

  > If you get stuck try searching how to change your DNS configuration online based on your router device
* Save your settings, reboot all your devices, and enjoy a network-wide ad-blocking experience.

## Use Pi-Hole as per device DNS Server

This approach is more tedious, but you can change the DNS Server used by default by your devices.

* Do a quick search on how to change the default DNS Server of your device
* Change the primary DNS Server address to your Pi-Hole Server

> This is not a recommended installation. Please be aware that you could encounter specific issues.

## **Pi-Hole Admin Panel**

* Go to `http://<yourpiholeip>`
* Log in with your password If you forgot the password, then connect via SSH to your server and run `sudo pihole -a -p`

![pihole-admin-panel.png]({{site.baseurl}}/img/user_upload/pihole-admin-panel.png)

From this panel, you'll be able to add/remove specific sites from your Adblocking experience.

Have fun!
