---
layout: single
title: Family Fun Trivia — Latest Posts
permalink: /
author_profile: true
author: Fam Fun Trivia
header:
  overlay_image: /assets/images/brand/cover-v1-2383x423.png
  overlay_filter: "0.3"   # optional, adds a dark overlay for text readability
  caption: "🎙️ Family Fun Trivia: The kid-friendly podcast"
---
<section class="home">

  {% assign recent_posts = site.posts | where_exp: "p", "p.published != false" | slice: 0, 4 %}

  {% if recent_posts.size == 0 %}
    <p>No posts yet. Check back soon!</p>
  {% else %}
    <div class="posts-list">
      {% for post in recent_posts %}
        <article class="post-excerpt">
          <h2 class="post-title">
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          </h2>

          <p class="post-meta">
            {{ post.date | date: "%B %-d, %Y" }}
            {% if post.categories and post.categories != empty %}
              • {{ post.categories | array_to_sentence_string }}
            {% endif %}
          </p>

          <div>
            <img src="{{ post.header.teaser }}" style="height: 150px; max-width: 400px;" />
          </div>

          <div class="post-summary">
            {% if post.excerpt %}
              {{ post.excerpt | strip_html | truncatewords: 100 }}
            {% else %}
              {{ post.content | markdownify | strip_html | truncatewords: 100 }}
            {% endif %}
          </div>

          <br/>
          <p class="read-more">
            <a href="{{ post.url | relative_url }}">Read more</a>
          </p>
        </article>
      {% endfor %}
    </div>
  {% endif %}
</section>

<div>
  <a href="/posts-grid/">All Blog Posts</a>
</div>