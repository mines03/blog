---
layout: page
title: Book
permalink: /books/
---

<h1>{{ page.title }}</h1>

<div class="bookshelf">
  {% for book in site.books %}
  <div class="book-item">
    <h2><a href="{{ book.url | relative_url }}">{{ book.title }}</a></h2>
    <p>by {{ book.author }}</p>
    {% if book.img %}
      <img src="{{ book.img | relative_url }}" alt="{{ book.title }}">
    {% endif %}
    <p>{{ book.excerpt | strip_html | truncatewords: 30 }}</p>
  </div>
  {% endfor %}
</div>
