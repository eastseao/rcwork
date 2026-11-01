---
layout: page
title: 归档
permalink: /archive/
---

{%- assign by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" -%}
{%- for year in by_year %}
<h2 id="y{{ year.name }}">{{ year.name }} 年 <span class="count">{{ year.items | size }} 篇</span></h2>
{%- assign by_month = year.items | group_by_exp: "post", "post.date | date: '%m'" -%}
{%- for month in by_month %}
<ul class="archive-list">
  <li class="archive-month">{{ month.name }} 月</li>
  {%- for post in month.items %}
  <li><span class="post-meta">{{ post.date | date: "%m-%d" }}</span><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
  {%- endfor %}
</ul>
{%- endfor %}
{%- endfor %}

{%- if site.posts.size == 0 %}
还没有任何笔记。
{%- endif %}
