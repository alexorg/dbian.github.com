---
layout: page
title: Just calm down, and listen.
tagline: 
---
{% include JB/setup %}









<h1 class="content-heading">Recent Posts</h1>
<ul>
  {% for post in site.posts limit:5 %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

