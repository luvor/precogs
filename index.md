---
layout: default
---

<div class="predictions-index">
  <div class="hero">
    <div class="hero-inner">
      <h1 class="hero-title">Precogs</h1>
      <p class="hero-subtitle">Архив предсказаний о будущем. Мини-эссе о том, что может случиться — и проверка, сбылось ли.</p>
    </div>
  </div>

  <h2 class="lang-section-title">Русский</h2>
  <ul class="post-list">
  {% assign ru_posts = site.posts | where: "lang", "ru" %}
  {% for post in ru_posts %}
    <li class="post-item">
      <h3 class="post-item-title"><a href="{{ post.url }}">{{ post.title }}</a></h3>
      <div class="post-item-meta">
        <time>{{ post.date | date: "%d.%m.%Y" }}</time>
        <span class="prediction-status status-{{ post.status }}">{% assign t = site.data.translations.ru %}{% assign sk = "status_" | append: post.status %}{{ t[sk] }}</span>
        {% if post.confidence %}<span>{{ post.confidence }}%</span>{% endif %}
      </div>
      <p class="post-item-excerpt">{{ post.excerpt | strip_html | truncate: 200 }}</p>
    </li>
  {% endfor %}
  </ul>

  <h2 class="lang-section-title">English</h2>
  <ul class="post-list">
  {% assign en_posts = site.posts | where: "lang", "en" %}
  {% for post in en_posts %}
    <li class="post-item">
      <h3 class="post-item-title"><a href="{{ post.url }}">{{ post.title }}</a></h3>
      <div class="post-item-meta">
        <time>{{ post.date | date: "%d.%m.%Y" }}</time>
        <span class="prediction-status status-{{ post.status }}">{% assign t = site.data.translations.en %}{% assign sk = "status_" | append: post.status %}{{ t[sk] }}</span>
        {% if post.confidence %}<span>{{ post.confidence }}%</span>{% endif %}
      </div>
      <p class="post-item-excerpt">{{ post.excerpt | strip_html | truncate: 200 }}</p>
    </li>
  {% endfor %}
  </ul>
</div>
