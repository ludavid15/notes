---
layout: page
title: Algorithms
permalink: /algorithms/
mathjax: true
date: 2021-05-11
---

<hr>

<div class="posts">
  {% for post in site.categories.algorithms %}
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