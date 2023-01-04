---
layout: page
title: Noticias
header: true
title_page: Noticias
order: 4
---

{% assign posts = site.posts | where: "categories","noticias" %}

<div class="posts">
  {% for post in posts %}
  <div class="post">
    <h2 class="post-title dd-post-title">
      <a href="{{ post.url }}">
        {{ post.title }} →
      </a>
    </h2>

    <span class="post-date">{{ post.date | date_to_string }}</span>

    <p>{{ post.description }}</p>

  </div>
  {% endfor %}
</div>