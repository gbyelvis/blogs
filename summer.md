---
bg: "owl.jpg"
layout: page
permalink: /posts/summer
title: "仲夏"
crawlertitle: "仲夏"
summary: "Posts about summer-elvis"
active: summer
---

{% for tag in site.tags %}
  {% assign t = tag | first %}
  {% assign posts = tag | last %}

  <ul class="year">
    {% for post in posts %}
      {% if post.tags contains "summer" %}
        <h2 class="category-key" id="{{ post.title | downcase }}"><a href="{{ post.url | relative_url}}">{{ post.title | capitalize }}</a></h2>
        <li>
          {% if post.lastmod %}
            <p>{{ post.summary }}</p>
            <span class="date">{{ post.lastmod | date: "%d-%m-%Y"  }}</span>
          {% else %}
            <p>{{ post.summary }}</p>
            <span class="date">{{ post.date | date: "%d-%m-%Y"  }}</span>
          {% endif %}  
        </li>
      {% endif %}
    {% endfor %}
  </ul>

{% endfor %}
