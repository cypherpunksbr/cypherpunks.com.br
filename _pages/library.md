---
permalink: /biblioteca/
layout: search
title: "Biblioteca"
last_modified_at: 2020-09-06
toc: true
---

{% assign sorted_cats = site.categories | sort %}
{% for category in sorted_cats %}
{% assign sorted_posts = category[1] | reversed %}
<ul>
  {% for post in sorted_posts %}
 	<li><a href="{{  post.url }}">{{  post.title }}</a></li>
  {% endfor %}
</ul>
{% endfor %}
