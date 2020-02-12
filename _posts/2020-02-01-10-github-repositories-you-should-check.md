---
layout: post
title: 10 Github Repositories you should check!
description: A curated list of awesome Open-source projects

categories: [ Top, Github ]
image: assets/images/github-top.jpg
author: stan_girard

---
This is a curated list of awesome projects that are Open-source on Github. I'm sure you'll find something useful in your quest from Primate to Developer.

## Nativefier

![Nativefier example ](/img/nativefier-example.gif "Nativefier example")

[Nativefier](https://github.com/jiahaog/nativefier) is a **command-line tool** to easily create a **desktop application for any web site** with succinct and minimal configuration. 

Apps are wrapped by [Electron](http://electron.atom.io/) in an OS executable (`.app`,`.exe`, etc.) for use on Windows, macOS and Linux.

You will be able to create an application on your computer for any website you'd like.

* Automatically retrieves the correct icon and app name.
* JavaScript and CSS injection.
* Flash Support (with [`--flash`](https://github.com/jiahaog/nativefier/blob/master/docs/api.md#flash) flag).
* Many more, see the [API docs](https://github.com/jiahaog/nativefier/blob/master/docs/api.md) or `nativefier --help`

**Installation**

```sh
npm install nativefier -g
```

Now run it on any website you want

```shell
nativefier --name "Primates" "https://primates.dev"
```

![Netlifier - Primates.dev  as an application](/img/netlifier-primates.png "Primates.dev Netlfier")

## Oh-My-Zsh

A delightful community-driven (with nearly 1,500 contributors) framework for managing your zsh configuration. Includes 200+ optional plugins (rails, git, OSX, hub, capistrano, brew, ant, php, python, etc), over 140 themes to spice up your morning, and an auto-update tool so that makes it easy to keep up with the latest updates

![ZSH Primates.dev](/img/nebirhos.jpg "ZSH Primates.dev")

Easy installation

```sh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

[Github](https://github.com/ohmyzsh/ohmyzsh) 

**Oh-My-Zsh** is probably one of the first thing you should install on a new environment. The project is updated frequently and the features are astonishing.

## Gitignore

This is **GitHub**’s collection of [`.gitignore`](http://git-scm.com/docs/gitignore) file templates. We use this list to populate the `.gitignore` template choosers available in the GitHub.com interface when creating new repositories and files.

For more information about how `.gitignore` files work, and how to use them, the following resources are a great place to start:

* The [Ignoring Files chapter](https://git-scm.com/book/en/Git-Basics-Recording-Changes-to-the-Repository#_ignoring) of the [Pro Git](http://git-scm.com/book) book.
* The [Ignoring Files article](https://help.github.com/articles/ignoring-files) on the GitHub Help site.
* The [gitignore](http://git-scm.com/docs/gitignore) manual page.

> Every time you start a new project you should go to Github Official [.gitignore](https://github.com/github/gitignore) and download the relevant .gitignore.

## Public APIs

The [Public API](https://github.com/public-apis/public-apis)'s Github Repository offers a collective list of free APIs for use in software and web development.

If you are looking for a specific API, this is the place to start looking for.

Here are a few links to the different APIs they reference 

* [Business](https://github.com/public-apis/public-apis#business)
* [Cloud Storage & File Sharing](https://github.com/public-apis/public-apis#cloud-storage--file-sharing)
* [Continuous Integration](https://github.com/public-apis/public-apis#continuous-integration)
* [Cryptocurrency](https://github.com/public-apis/public-apis#cryptocurrency)
* [Currency Exchange](https://github.com/public-apis/public-apis#currency-exchange)
* [Data Validation](https://github.com/public-apis/public-apis#data-validation)
* [Development](https://github.com/public-apis/public-apis#development)
* [Test Data](https://github.com/public-apis/public-apis#test-data)
* [Text Analysis](https://github.com/public-apis/public-apis#text-analysis)
* [Tracking](https://github.com/public-apis/public-apis#tracking)
* [Transportation](https://github.com/public-apis/public-apis#transportation)
* [URL Shorteners](https://github.com/public-apis/public-apis#url-shorteners)
* [Video](https://github.com/public-apis/public-apis#video)
* [Weather](https://github.com/public-apis/public-apis#weather)

## The Fuck

Despite the name, *[The Fuck](https://github.com/nvbn/thefuck)* is a magnificent app that corrects errors in previous console commands.

![The Fuck example gif Primates.dev](/img/thefuck-example.gif "The Fuck Example")

### Easy Installation

On OS X, you can install *The Fuck* via [Homebrew](https://brew.sh/)(or via [Linuxbrew](https://linuxbrew.sh/)on Linux):

```shell
brew install thefuck
```

On Ubuntu / Mint, install *The Fuck* with the following commands:

```shell
sudo apt update
sudo apt install python3-dev python3-pip python3-setuptools
sudo pip3 install thefuck
```

On other systems, install*The Fuck* by using `pip`:

```shell
pip install thefuck
```

### Examples

```shell
➜ apt-get install vim
E: Could not open lock file /var/lib/dpkg/lock - open (13: Permission denied)
E: Unable to lock the administration directory (/var/lib/dpkg/), are you root?

➜ fuck
sudo apt-get install vim [enter/↑/↓/ctrl+c]
[sudo] password for nvbn:
Reading package lists... Done
...
```

```shell
➜ git brnch
git: 'brnch' is not a git command. See 'git --help'.

Did you mean this?
    branch

➜ fuck
git branch [enter/↑/↓/ctrl+c]
* master
```

## Netdata

**[Netdata](https://github.com/netdata/netdata)** is **distributed, real-time, performance and health monitoring for systems and applications**. It is a highly-optimized monitoring agent you install on all your systems and containers.

Netdata provides **unparalleled insights**, **in real-time**, of everything happening on the systems it runs (including web servers, databases, applications), using **highly interactive web dashboards**. It can run autonomously, without any third-party components, or it can be integrated to existing monitoring toolchains (Prometheus, Graphite, OpenTSDB, Kafka, Grafana, and more).

Netdata is **fast** and **efficient**, designed to permanently run on all systems (**physical** & **virtual** servers, **containers**, **IoT**devices), without disrupting their core function.

Netdata is **free, open-source software** and it currently runs on **Linux**, **FreeBSD**, and **MacOS**, along with other systems derived from them, such as **Kubernetes** and **Docker**.

![Netdata Gif Primates.dev](/img/netdata-primates.gif "Netdata Gif Primates.dev")

### Easy Installation

To install Netdata from source on any Linux system (physical, virtual, container, IoT, edge) and keep it up to date with the **nightly releases** automatically, run the following:

```shell
# make sure you run `bash` for your shell
bash

# install Netdata directly from GitHub source
bash <(curl -Ss https://my-netdata.io/kickstart.sh)
```

## Resume

**[Resume](https://github.com/resume/resume.github.com) is a service that creates a résumé based on your GitHub repos/activity.**

![Resume Stan Girard Primates.dev](/img/resume-github.png "Resume StanGirard Primates.dev")

All you have to do is go to **[Resume](https://github.com/resume/resume.github.com)**, then give your username and Resume will generate your Online CV based on [Github](https://github.com/) public activity.

It is based on:

* Github Profile information
* Your website
* The languages of the different projects your worked on
* Your popular repositories
* Your contributions to other repositories

## Serverless

![Serverless Framework Primates.dev](/img/serverless-framework-primates.gif "Serverless Framework Primates.dev")

**[The Serverless Framework](https://github.com/serverless/serverless)** – Build applications comprised of microservices that run in response to events, auto-scale for you, and only charge you when they run. This lowers the total cost of maintaining your apps, enabling you to build more logic, faster.

The Framework uses new event-driven compute services, like AWS Lambda, Google Cloud Functions, and more. It's a command-line tool, providing scaffolding, workflow automation and best practices for developing and deploying your serverless architecture. It's also completely extensible via plugins.

### Features

* Supports Node.js, Python, Java, Go, C#, Ruby, Swift, Kotlin, PHP, Scala, & F#
* Manages the lifecycle of your serverless architecture (build, deploy, update, delete).
* Safely deploy functions, events and their required resources together via provider resource managers (e.g., AWS CloudFormation).
* Functions can be grouped ("serverless services") for easy management of code, resources & processes, across large projects & teams.
* Minimal configuration and scaffolding.
* Built-in support for multiple stages.
* Optimized for CI/CD workflows.

### Examples

Here is a list [Serverless Examples](https://github.com/serverless/examples) for different applications

## Hyper

[Hyper](https://hyper.is/) is a beautiful and extensible experience for command-line interface users, built on open web standards. In the beginning, our focus will be primarily around speed, stability and the development of the correct API for extension authors.

![HyperJS Primates.dev Terminal](/img/hyperapp.gif "HyperJS Primates.dev Terminal")

Download [here](https://hyper.is/)

## Free For Dev

[Free For Dev](https://github.com/ripienaar/free-for-dev) is a list of software (SaaS, PaaS, IaaS, etc.) and other offerings that have free tiers for developers.

The scope of this particular list is limited to things infrastructure developers (System Administrator, DevOps Practitioners, etc.) are likely to find useful.

Please feel free to let us know in the commentaries of other awesome projects that you know of.
