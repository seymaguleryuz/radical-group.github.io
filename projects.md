---
title: Projects
permalink: /projects/
---
{% assign proj_array = "active|inactive" |split: "|" %}

## Projects

RADICAL engages in computing research to enable advances in cyberinfrastructure design and development. RADICAL contributes to address a diverse set of scientific problems at scale, ranging from biomolecular sciences to earth sciences and high-energy physics.

{% for item in proj_array %}
<div class="pos_header">
 {% if item == 'active' %}
<h3>Current</h3>
 {% elsif item == 'inactive' %}
<h3>Past</h3>
{% endif %}
</div>

<div class="content list projects">
  {% for post in site.projects %}
     {% if post.status == item %}
     <div class="list-item-projects">
      <p align="justify" class="list-post-title">
            <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>: {{ post.abstract }}<br>{{ post.grant_number }}<br>
      </p>
    </div>
    {% endif %}
  {% endfor %}
</div>

{% endfor %}
