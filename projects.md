---
title: Projects
permalink: /projects/
---

## Projects

Here you can find currently active and past research projects the Lab was involved with:

### Active Projects
<div class="content list projects">
  {% for post in site.projects %}
    <div class="list-item-projects">
      <p align="justify" class="list-post-title">
        <a href="{{ site.baseurl }}{{ post.url }}"> <dl><li> {{ post.title }}: <small>{{ post.abstract }}<br>{{ post.grant_number }}</small></li></dl></a>
      </p>
    </div>
  {% endfor %}
</div>

### Past projects