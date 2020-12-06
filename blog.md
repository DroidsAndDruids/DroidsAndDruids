---
layout: page
title: Blog
title_page: Blog
order: 3
---

{% assign posts = site.posts | where: "categories","blog" %}

<div class="posts">
  {% for post in posts %}
  {% assign author = post.author.first %}
  <div class="post">
    <h1 class="post-title">
      <a href="{{ post.url }}">
        {{ post.title }} →
      </a>
    </h1>

    <span class="post-date">{{ post.date | date_to_string }}</span>

    <p class="dd-post--author">por {{ author.name }}</p>
    <p>{{ post.description }}</p>

  </div>
  {% endfor %}
</div>
