---
layout: page
title: Tristan Dietz
subtitle: 'Things, stuff...'
name: tristan_dietz
display_name: Tristan Dietz
email: tristan.dietz@greenly.dev
web: https://primates.dev/authors/tristandietz
css: /css/aboutme.css
published: true
---

<div id="aboutme-section">

    <p class="about-text">
        <span class="fa fa-briefcase about-icon"></span>
        Currently at Natixis and <strong>student</strong> at <strong>Epita</strong>.
    </p>

    <p class="about-text">
        <span class="fa fa-graduation-cap about-icon"></span>
        Studying Computer Science at <strong>Epita</strong>
    </p>

    <p class="about-text">
        <span class="fa fa-globe about-icon"></span>
        Actually in <i>Paris</i>.
    </p>

</div>

<div id="contactme-section">
    <h1 id="contact">Contact</h1>


    <p>You can contact me on <a href="https://www.linkedin.com/in/tristan-dietz/">LinkedIn</a>.</p>

</div>

<div id="contactme-section">
    <h1 id="contact">My Articles</h1>

    <div class="posts-list">
        {% for post in site.posts %}
        {% if post.author contains page.author %}
        <article class="post-preview">
            <a href="{{ post.url | relative_url }}">
                <h2 class="post-title">{{ post.title }}</h2>
            </a>
            {% if post.tags.size > 0 %}
            <div class="blog-tags">
                Tags:
                {% if site.link-tags %}
                {% for tag in post.tags %}
                <a href="{{ '/tags' | relative_url }}#{{- tag -}}">{{- tag -}}</a>
                {% endfor %}
                {% else %}
                {{ post.tags | join: ", " }}
                {% endif %}

            </div>
            {% endif %}
        </article>
        {% endif %}
        {% endfor %}

    </div>
</div>