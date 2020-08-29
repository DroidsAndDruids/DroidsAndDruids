---
layout: default
title: Home
---

## Último episodio

<div class="posts">
  {% for post in site.posts limit: 1 %}
  <div class="post">
    <h3 class="post-title">
      <a href="{{ post.url }}">
        {{ post.title }}
      </a>
    </h3>

    <span class="post-date">{{ post.date | date_to_string }}</span>

    <p>{{ post.description }}</p>

    <iframe id="audio_{{post.audio}}" frameborder='0' allowfullscreen='' scrolling='no' height='200' style='border:1px solid #EEE; box-sizing:border-box; width:100%;' src="https://www.ivoox.com/player_ej_{{post.audio}}_4_1.html?c1=ff6600"></iframe>

  </div>
  {% endfor %}
</div>
