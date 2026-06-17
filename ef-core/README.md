---
layout: default
title: EF Core Posts
---

# EF Core

# EF Core links

- [EF Core mental Model & DBConetxt](ef-core-model.md)

{% for post in site.pages %}
  {% if post.path contains 'ef-core/' and post.name != 'README.md' %}
  <article class="post">
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    {{ post.content }}
  </article>
  <hr>
  {% endif %}
{% endfor %}

