---
layout: default
title: Latest News
permalink: /news/
---

<section class="section news-page">
  <p class="eyebrow">PROJECT JOURNAL</p>
  <h1>Latest News</h1>
  <p class="section-description">
    Updates, discoveries and progress from the projects.
  </p>

  <div class="news-list">
    {% for post in site.posts %}
      <a class="news-card-link" href="{{ post.url | relative_url }}">
        <article class="news-card">
          <p class="news-meta">
            <time datetime="{{ post.date | date_to_xmlschema }}">
              {{ post.date | date: "%d.%m.%Y" }}
            </time>
            {% for category in post.categories %}
              <span class="news-category">
                {{ category | replace: "-", " " }}
              </span>
            {% endfor %}
          </p>
          <h2 class="news-card-title">{{ post.title }}</h2>
          {% if post.excerpt %}
            <p>{{ post.excerpt | strip_html | truncate: 220 }}</p>
          {% endif %}
          <span class="text-link">Read update →</span>
        </article>
      </a>
    {% endfor %}
    {% unless site.posts.size > 0 %}
      <p class="news-empty">
        No updates yet. New project stories will appear here.
      </p>
    {% endunless %}
  </div>
</section>
