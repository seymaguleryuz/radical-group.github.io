---
title: Blog
permalink: /blog/
---

{% assign blogs_sorted = site.blog | sort: 'date' | reverse %}

### **Blog Posts from the lab**

<div class="content list">
  {% for post in blogs_sorted %}
    <div class="list-item">
    <p class="list-post-title">
        <a href="{{ site.baseurl }}{{ post.url }}">- {{ post.title }}</a> (<small>{{post.date | date: "%m/%d/%y" }}</small>)
        </p>
    </div>
  {% endfor %}
</div>
