---
layout: page
title: Stanislas Girard
subtitle: 'My Impressive boring life :D'
name: stan_girard
display_name: Stanislas Girard
email: girard.stanislas@pm.me
web: 'https://primates.dev/authors/stangirard'
css: /css/aboutme.css
position: Chief Editor
---

<div id="aboutme-section">

    <p class="about-text">
        <span class="fa fa-briefcase about-icon"></span>
        Currently a <strong>Blockchain Dev & DevOps</strong> at Natixis and <strong>Student </strong> at
        <strong>Epita</strong>.
    </p>

    <p class="about-text">
        <span class="fa fa-graduation-cap about-icon"></span>
        Studying Computer Science at <strong>Epita</strong>
    </p>

    <p class="about-text">
        <span class="fa fa-code about-icon"></span>
        I enjoy writing <strong>useful & reusable software tools</strong> to help others &mdash; check out <a
            href="https://github.com/StanGirard">my projects</a>. I pretty much enjoy working on anything.
    </p>

    <p class="about-text">
        <span class="fa fa-heart about-icon"></span>
        I love making cakes, <strong>travelling</strong> at any given (and non-given) moment, learning new things,
        and meeting new people :)
    </p>

    <p class="about-text">
        <span class="fa fa-globe about-icon"></span>
        Grew up in <i>Le Pecq, France</i>; moved to <i>Kansas City, USA</i> for my last year of High School ; studying
        in <i>Paris</i> at <i>Epita</i> to become a computer scientist.
    </p>

</div>

<div id="contactme-section">
    <h1 id="contact">Contact</h1>


    <p>You can <a href="mailto:girard.stanislas@protonmail.com.com?subject=Hello from Primates.dev">email me</a> if you
        want to get in touch.</p>

</div>

<div id="contactme-section">
<h1 id="contact">My Articles</h1>

<div class="posts-list">
    {% for post in site.posts %}
    {% if post.author contains page.name %}
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
