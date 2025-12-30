---
layout: default
---

<ul>
{% for post in site.posts %}
  <li style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px;">
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    
    {% if post.post_icon %}
      <img src="{{ post.post_icon | relative_url }}" style="width: 64px; height: 64px;">
    {% endif %}
  </li>
{% endfor %}
</ul>