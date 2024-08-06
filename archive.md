---
layout: toc
title: Archive
---
Browse all posts by month and year.

{% assign postsByYearMonth = site.posts | group_by_exp: "post", "post.date | date: '%B %Y'" %}
{% for yearMonth in postsByYearMonth %}
  <h2 class="yearmonth">{{ yearMonth.name }}</h2>
  <ul>
    {% for post in yearMonth.items %}
      <li><span>{{ post.date | date: "%-d"}}</span><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
