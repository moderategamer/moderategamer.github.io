[← Back to Home]({{ '/' | relative_url }})

# EF Core — All Posts

{% for post in site.pages %}
  {% if post.path contains 'ef-core/' and post.name != 'README.md' %}
  <article class="post">
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    {{ post.content }}
  </article>
  <hr>
  {% endif %}
{% endfor %}

