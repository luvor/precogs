---
layout: default
---

<div class="predictions-index">
  <div class="hero">
    <div class="hero-inner">
      <div class="hero-eyebrow">Predictions Archive</div>
      <h1 class="hero-title">Видим <span class="hero-title-glow">будущее</span> раньше,<br>чем оно наступит</h1>
      <p class="hero-subtitle">Мини-эссе о том, что может произойти — с данными, аргументами и честной проверкой временем. Каждое предсказание получает статус и дату верификации.</p>
    </div>
  </div>

  <div class="index-content">
    <div class="lang-section">
      <h2 class="lang-section-title">Русский</h2>
      <ul class="cards-grid">
      {% assign ru_posts = site.posts | where: "lang", "ru" %}
      {% for post in ru_posts %}
        <li class="prediction-card animate-on-scroll">
          <div class="card-header">
            <h3 class="card-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
          </div>
          <div class="card-meta">
            <time>{{ post.date | date: "%d.%m.%Y" }}</time>
            <span class="prediction-status status-{{ post.status }}">{% assign t = site.data.translations.ru %}{% assign sk = "status_" | append: post.status %}{{ t[sk] }}</span>
          </div>
          <p class="card-excerpt">{{ post.excerpt | strip_html | truncate: 160 }}</p>
          <div class="card-footer">
            {% if post.confidence %}
            <div class="card-confidence">
              <div class="confidence-bar"><div class="confidence-bar-fill" style="width: {{ post.confidence }}%"></div></div>
              <span>{{ post.confidence }}%</span>
            </div>
            {% else %}
            <div></div>
            {% endif %}
            <span class="card-read-more">Читать</span>
          </div>
        </li>
      {% endfor %}
      </ul>
    </div>

    <div class="lang-section">
      <h2 class="lang-section-title">English</h2>
      <ul class="cards-grid">
      {% assign en_posts = site.posts | where: "lang", "en" %}
      {% for post in en_posts %}
        <li class="prediction-card animate-on-scroll">
          <div class="card-header">
            <h3 class="card-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
          </div>
          <div class="card-meta">
            <time>{{ post.date | date: "%d.%m.%Y" }}</time>
            <span class="prediction-status status-{{ post.status }}">{% assign t = site.data.translations.en %}{% assign sk = "status_" | append: post.status %}{{ t[sk] }}</span>
          </div>
          <p class="card-excerpt">{{ post.excerpt | strip_html | truncate: 160 }}</p>
          <div class="card-footer">
            {% if post.confidence %}
            <div class="card-confidence">
              <div class="confidence-bar"><div class="confidence-bar-fill" style="width: {{ post.confidence }}%"></div></div>
              <span>{{ post.confidence }}%</span>
            </div>
            {% else %}
            <div></div>
            {% endif %}
            <span class="card-read-more">Read</span>
          </div>
        </li>
      {% endfor %}
      </ul>
    </div>
  </div>
</div>
