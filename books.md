---
layout: default
title: My Bookshelf
---

# 📚 My Bookshelf

<ul class="book-list">
  {% assign sorted_books = site.books | sort: 'date_read' | reverse %}
  {% for book in sorted_books %}
    <li>
      <a href="{{ book.url }}">
        <strong>{{ book.title }}</strong> by {{ book.author }}
        {% if book.rating %} — {{ book.rating }}★ {% endif %}
        <em>({{ book.status }})</em>
      </a>
    </li>
  {% endfor %}
</ul>
