---
layout: page
title: Just calm down, and listen.
tagline: 
---
{% include JB/setup %}








## Recent Posts ##
<ul>
  {% for post in site.posts limit:5 %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

