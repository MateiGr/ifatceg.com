---
title: Archive
layout: default
---

{% assign postsByMonth = site.posts | group_by_exp:"post", "post.date | date: '%B %Y'" %}
{% for month in postsByMonth %}
  <h2>{{ month.name }}</h2>
  <ul>
    {% for post in month.items %}
      <li>{{ post.date | date: "%d %B %Y" }} - <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}

