---
layout: page
title: Book
permalink: /books/
---

# {{ page.title }}

<div class="bookshelf-grid">
  {% for book in site.books %}
  <div class="book-card">
      {% if book.img %}
      <a href="#" onclick="alert('URL Buku: {{ book.url | relative_url }}'); return false;">
      <img src="{{ book.img | relative_url }}" alt="{{ book.title }} cover" class="book-cover"/>
      </a>
      {% endif %}
    <a href="{{ book.url | relative_url }}">
      <h3 class="book-title">{{ book.title }}</h3>
    <p class="book-author">{{ book.author }}</p>
    </a>
      {% if book.rating %}
    <p class="book-author">{{ book.rating }}</p>
      {% endif %}
  </div>
  {% endfor %}
</div>

<style>
.bookshelf-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
  gap: 1rem;
}
.book-card {
  border: 1px solid #ddd;
  padding: 0.75rem;
  text-align: center;
  background: #fafafa;
  border-radius: 6px;
  transition: box-shadow 0.3s ease;
}
.book-card:hover {
  box-shadow: 0 4px 12px rgba(0,0,0,0.15);
}
.book-cover {
  max-width: 100%;
  height: auto;
  border-radius: 4px;
  margin-bottom: 0.5rem;
}
.book-title {
  font-size: 1.1rem;
  margin: 0.25rem 0;
}
.book-author {
  font-style: italic;
  color: #666;
  font-size: 0.9rem;
  margin: 0;
}
</style>
