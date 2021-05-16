---
layout: page
title: Dynamics and Controls
permalink: /dynamics/
date: 2021-05-05
---

<hr>

<div class="posts">
  {% for post in site.categories.dynamics %}
  <div class="post">
    <h2 class="post-title">
      <a href="{{ post.url | relative_url }}">
        {{ post.title }}
      </a>
    </h2>

    <span class="post-date">{{ post.date | date_to_string }}</span>
    {{ post.excerpt }}
    <a href="{{ post.url | relative_url }}">
    Read on
    </a>
  </div>
  <hr>
  {% endfor %}
</div>