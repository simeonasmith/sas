---
layout: default
title: Archive
permalink: /archive/
---

<section>
  <div class="section-heading">
    <h2>Archive</h2>
    <p>All published articles.</p>
  </div>

  <div class="archive-list">
    {% for post in site.posts %}
      <article class="archive-item">
        <a href="{{ post.url | relative_url }}">
          <h3>{{ post.title }}</h3>
          <p class="subtitle">{{ post.subtitle | default: post.excerpt | strip_html | truncate: 150 }}</p>
        </a>
        <div class="meta">{{ post.date | date: "%-d %B %Y" }}</div>
      </article>
    {% endfor %}
  </div>
</section>
