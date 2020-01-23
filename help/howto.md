---
layout: page
title: How to Post an Article
subtitle: Guidelines to help you post an article
published: true
bigimg: /img/user_big_img/writing-post.jpg
date: '2020-01-23'
gh-repo: StanGirard/Primates
gh-badge:
  - star
  - watch
  - fork
  - follow
---


Here are a few steps to help you get started on blogging

## Get Started

### Fork Primates Repo
---

First of all you need to fork the project

> You need to have a github account

![fork-primates.png]({{site.baseurl}}/img/user_upload/fork-primates.png)



### Setup Github Pages on Fork
---

Do this step only if you want to be able to visualize your post before making a pull request to the main repo

Then you need to host the Fork on Github Pages

- Go to Settings
- Choose Master Branch
- Don't choose a theme
- Optional: Add a custom domain (follow this [guide](https://help.github.com/en/github/working-with-github-pages/configuring-a-custom-domain-for-your-github-pages-site))

![fork-github-pages.png]({{site.baseurl}}/img/user_upload/fork-github-pages.png)

### Check that your installation works
---

Go to `<yourGithubUsername>.github.io/Primates` to see if the github pages work

If that is successfull then your installation is complete
  



## Post an Article


### Go to [Prose.io](http://prose.io)
---

![prose-login.png]({{site.baseurl}}/img/user_upload/prose-login.png)

Give access to Prose to your Github Account

### Go to Primates Project
---

Choose your Primates Project

![prose-primate-chose.png]({{site.baseurl}}/img/user_upload/prose-primate-chose.png)

If everything is successfull you should end up on a page that looks like that.

![prose-archi.png]({{site.baseurl}}/img/user_upload/prose-archi.png)


- _data: Stores information about the authors, etc
- _post: Place where the posts are saved
- help: Page that are added such as this one

### Create an author

Go to **_data** and modify **authors.yml**

Add a new author:

```YAML
<username>:
    name: <First LastName>
    email: <Email>
    web: <Your website or Profile Page>
```

Don't forget to save !

### Create a post

Go **_post** and click on the **create button**




