---
layout: page
title: podcast
title_page: El Podcast
order: 1
---

{% assign posts = site.posts | where: "categories","podcast" %}

<div class="posts">
  {% for post in posts %}
  <div class="post">
    <h3 class="post-title">
      <a href="{{ post.url }}">
        {{ post.title }} →
      </a>
    </h3>

    <span class="post-date">{{ post.date | date_to_string }}</span>

    <p>{{ post.description }}</p>

    <iframe id="audio_{{post.audio}}" frameborder='0' allowfullscreen='' scrolling='no' height='200' style='border:1px solid #EEE; box-sizing:border-box; width:100%;' src="https://www.ivoox.com/player_ej_{{post.audio}}_4_1.html?c1=ff6600"></iframe>

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
