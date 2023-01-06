---
layout: default
title: Home
---

{% assign posts = site.posts | where: "categories","noticias" %}

<div class="posts">
  {% for post in posts %}
  <div class="post">
    <h2 class="post-title dd-post-title">
      <a href="{{ post.url }}">
        {{ post.title }}
      </a>
    </h2>

    <span class="post-date">{{ post.date | date_to_string }}</span>

    <p>{{ post.description }}</p>

  </div>
  {% endfor %}
</div>

{% if posts.size > 5 %}
<div class="pagination">
    {% if paginator.next_page %}
      <a class="pagination-item older" href="page{{paginator.next_page}}">Atrás</a>
    {% else %}
      <span class="pagination-item older">Atrás</span>
    {% endif %}
    {% if paginator.previous_page %}
      {% if paginator.page == 2 %}
        <a class="pagination-item newer" href="">Adelante</a>
      {% else %}
        <a class="pagination-item newer" href="page{{paginator.previous_page}}">Adelante</a>
      {% endif %}
    {% else %}
      <span class="pagination-item newer">Adelante</span>
    {% endif %}
</div>
{% endif %}
