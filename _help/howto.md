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

First of all, you need to fork the project.

> You need to have a GitHub account

![fork-primates.png]({{site.baseurl}}/img/user_upload/fork-primates.png)



### Setup Github Pages on Fork
---

Do this step only if you want to be able to visualize your Post before making a pull request to the principal repository.

Then it would be best if you hosted the Fork on Github Pages.

- Go to Settings
- Choose Master Branch
- Don't choose a theme
- Optional: Add a custom domain (follow this [guide](https://help.github.com/en/github/working-with-github-pages/configuring-a-custom-domain-for-your-github-pages-site))

![fork-github-pages.png]({{site.baseurl}}/img/user_upload/fork-github-pages.png)

### Check that your installation works
---

Go to `<yourGithubUsername>.github.io/Primates` to see if the GitHub pages work.

If that is successful, then your installation is complete.
  



## Post an Article


### Go to [Prose.io](http://prose.io)
---

![prose-login.png]({{site.baseurl}}/img/user_upload/prose-login.png)

Give access to Prose to your Github Account.

### Go to Primates Project
---

Choose your Primates Project

![prose-primate-chose.png]({{site.baseurl}}/img/user_upload/prose-primate-chose.png)

If everything is successful, you should end up on a page that looks like that.

![prose-archi.png]({{site.baseurl}}/img/user_upload/prose-archi.png)


- _data: Stores information about the authors, etc
- _post: Place where the posts are saved
- help: Pages that are added such as this one

### Create an author

Go to **_data** and modify **authors.yml**

Add a new author:

```YAML
<username>:
    name: <First LastName>
    email: <Email>
    web: <Your website or Profile Page>
```

Don't forget to save it!

### Create a post

Go **_post** and click on the **create button**

![post-create-metadata.png]({{site.baseurl}}/img/user_upload/post-create-metadata.png)

Then click on the metadata on the right.

Metadata:
- Subtitle: subtitle of the article
- Big image: landscape image at the top of the article. It must be in the **img/user_big_img** folder
- Image: Little image in a circle that represents your Post. Must be chosen from the images in the folders already in **img/**
- Author: Add your author username
- Tags: Add the tags for your article
- Date: Add the date YYYY-MM-DD
- Publish: Set to false to save it as a draft

**Then start writing your article !**

## Pull Request

Once you are done with your article, make a pull request to merge your project with the main repo.
If you've followed all the guidelines, the article should then be accepted within a day.


At any time you can see the changes to your article on the `http://<yourGithubUsername>.github.io/Primates`

Good luck!
