---
layout: page
title: Revista
title_page: La Revista
order: 2
---

<section class="dd-revista-info">
Una revista digital de ciencia ficción y género fantástico, cuyos números se publicará en la plataforma Lektu bajo ISSN.
Aquí encontraras todo lo relacionado con nuestra revista, ¡sigue leyendo para no perderte nada!
</section>

{% assign posts = site.posts | where: "categories","revista" %}

<div class="posts dd-revista-posts">
  {% for post in posts %}
  <div class="post dd-revista-post">
    {% if post.image %}
    <div class="dd-revista-image">
      <a
        class="book-container"
        href="{{ post.url }}"
        rel="noreferrer noopener"
      >
        <div class="book">
          <img
            alt="Logo revista"
            src="{{ site.baseurl }}{{ post.image }}"
            />
        </div>
      </a>
    </div>
    {% endif %}
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
