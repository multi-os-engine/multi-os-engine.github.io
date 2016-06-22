---
title: "Blog"
layout: archive
excerpt: ""
sitemap: false
permalink: /blog/
---

{% include base_path %}

<div class="grid__wrapper">
  {% assign blogposts = site.blogposts | reverse %}
  {% for post in blogposts %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>
