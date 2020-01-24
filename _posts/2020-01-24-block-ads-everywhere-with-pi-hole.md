---
layout: post
published: true
title: Block Ads everywhere with Pi-hole
subtitle: A DNS sinkhole that protects your devices from ads
author: stan_girard
tags:
  - Ads
  - AdBlock
image: /img/user_upload/Pi-hole_Logo.png
date: '2020-01-24'
categories:
  - Ads
---
[Pi-hole](https://pi-hole.net/) allows you to block all the ads without even installing an ad blocker on your device. 
One of the main advantages of [Pi-hole](https://pi-hole.net/) is that you can use it anywhere you like (TVs, smartphones, etc)

- **Easy to Install - Less than 10 minutes**
- **Content is blocked before reaching your device**
- **Open Source therefore free**
- **Very fast & Reliable**

## Installation

In order to install [Pi-hole](https://pi-hole.net/) you'll either need a [Raspbery-Pi 4/3](https://amzn.to/38InYI1) or a small server such as one on [DigitalOcean](https://m.do.co/c/f9dca2b1ecc8)

For the purpose of simplicity I'll show you how to install it on [DigitalOcean](https://m.do.co/c/f9dca2b1ecc8)

### DigitalOcean

If you already have an account you can skip to step 2.

1. **Create an account on DigitalOcean** [here](https://m.do.co/c/f9dca2b1ecc8).
2. **Create a Droplet**
![digitalocean-create-droplet.png]({{site.baseurl}}/img/user_upload/digitalocean-create-droplet.png)
	- Choose **Ubuntu**
![digitalocean-image.png]({{site.baseurl}}/img/user_upload/digitalocean-image.png)

    - Choose the **1GB/1CPU** Option
![digitalocean-size.png]({{site.baseurl}}/img/user_upload/digitalocean-size.png)

    - Choose the **location that best suits your needs**
![digitalocean-location.png]({{site.baseurl}}/img/user_upload/digitalocean-location.png)
    - Add an **SSH Key for better protection** or use the One-time Password
![digitalocean-sshkeys.png]({{site.baseurl}}/img/user_upload/digitalocean-sshkeys.png)
	- Create the droplet
    
The deployment of the drop should take less than 2 minutes.

Once the droplet has been deployed, look for its IP address.

Then just log to your Droplet
{% highlight bash %}
# SSH to your droplet
ssh root@<ipaddress>
{% endhighlight %}
  
### Installation
  
Simply run 

{% highlight bash %}
# One line installer
 curl -sSL https://install.pi-hole.net | bash

{% endhighlight %}
 

    
