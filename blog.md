---
layout: page
title: Blog
title_page: Blog
order: 3
---

En construcción

{% assign posts = site.posts | where: "categories","blog" %}

<div class="posts">
  {% for post in posts %}
  <div class="post">
    <h1 class="post-title">
      <a href="{{ post.url }}">
        {{ post.title }} →
      </a>
    </h1>

    <span class="post-date">{{ post.date | date_to_string }}</span>

    <p>{{ post.description }}</p>

  </div>
  {% endfor %}
</div>