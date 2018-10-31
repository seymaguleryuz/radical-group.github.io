---
title: News
permalink: /news/
---

### **News from the lab**

<div class="content list">
  {% for post in site.news %}
    <div class="list-item">
    <p class="list-post-title">
        <a href="{{ site.baseurl }}{{ post.url }}">- {{ post.title }}</a> (<small>{{post.date | date: "%m/%d/%y" }}</small>)
        </p>
    </div>
  {% endfor %}
</div>
