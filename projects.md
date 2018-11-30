---
title: Projects
permalink: /projects/
---
{% assign proj_array = "active|inactive" |split: "|" %}

## Projects

Current and past research projects of the Lab.

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
       {% if post.logo %}
        <img src="{{site.baseurl}}/images/projects/{{post.logo}}" alt="Project image">
        {% else %}
        <img src="{{site.baseurl}}/images/projects/mgray_800x600.png alt="Project image">
        {% endif %}	    	
	     	<span class="list-post-title" >
	     		<a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>: {{ post.abstract }}
	     		<!-- <br>{{ post.grant_number }} -->
	      </span>
	    </div>
  	{% endif %}
	{% endfor %}
</div>

{% endfor %}
