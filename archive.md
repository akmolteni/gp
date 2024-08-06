---
layout: toc
title: Archive
---

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur vel quam aliquam, tincidunt mi ut, luctus arcu. Phasellus eget odio eros. Curabitur justo urna, egestas quis eros non, feugiat porta diam. Aenean felis ex, placerat ut augue eget, efficitur maximus elit. Nulla ut massa ligula. Suspendisse lacus ante, feugiat id feugiat quis, egestas et nibh. Cras non risus pretium, pellentesque sem et, vulputate nibh. Mauris volutpat fringilla nisi, at gravida libero egestas vitae.

Browse all posts by month and year.

{% assign postsByYearMonth = site.posts | group_by_exp: "post", "post.date | date: '%B %Y'" %}
{% for yearMonth in postsByYearMonth %}
  <h2>{{ yearMonth.name }}</h2>
  <ul>
    {% for post in yearMonth.items %}
      <li><span>{{ post.date | date: "%-d"}}</span><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
