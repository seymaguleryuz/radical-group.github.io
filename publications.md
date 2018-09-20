---
title: Publications
permalink: /publications/
---

{% assign pub_sorted = (site.publications | sort: 'date') %}
{% assign pub_array = "pub|standard|draft" | split: "|" %}
{% assign year_array = "2018|2017|2016|2015|2014|2013|2012|2011|2010|2009|2008|2007|2006|2005" | split: "|" %}

{% for item in pub_array %}

<div class="pos_header">
{% if item == 'pub' %}
<h3>Publications</h3>
{% elsif item == 'standard' %}
<h3>Standards, White Papers, Technical Reports</h3>
{% elsif item == 'draft' %}
<h3>Draft</h3>
{% endif %}
</div>

{% if item == 'pub' %}
{% for year in year_array %}
<div class="pos_header">
{% if year == '2018' %}
    <h4>2018</h4>
{% elsif year == '2017' %}
    <h4>2017</h4>
{% elsif year == '2016' %}
    <h4>2016</h4>
{% elsif year == '2015' %}
    <h4>2015</h4>
{% elsif year == '2014' %}
    <h4>2014</h4>
{% elsif year == '2013' %}
    <h4>2013</h4>
{% elsif year == '2012' %}
    <h4>2012</h4>
{% elsif year == '2011' %}
    <h4>2011</h4>
{% elsif year == '2010' %}
    <h4>2010</h4>
{% elsif year == '2009' %}
    <h4>2009</h4>
{% elsif year == '2008' %}
    <h4>2008</h4>
{% elsif year == '2007' %}
    <h4>2007</h4>
{% elsif year == '2006' %}
    <h4>2006</h4>
{% elsif year == '2005' %}
    <h4>2005</h4>
{% endif %}
</div>
<div class="content list people" align="left">
{% for pub in pub_sorted reversed %}
{% assign date = pub.date | date_to_long_string %}
{% if pub.type contains item and date contains year %}
<div class="list-item-pub">
<p class="list-post-title" align="left">
<a class="name" href="{{ site.baseurl }}{{ pub.url }}"> <dl style="font-size:0.7rem;"><li> 
{{ pub.title }}<br>{{ pub.author }}<br>{{ pub.venue }}</li></dl></a>
</p>
</div>
{% endif %}
{% endfor %}
</div>
{% endfor %}
{% else %}
<div class="content list people" align="left">
{% for pub in pub_sorted reversed %}
{% if pub.type contains item %}
<div class="list-item-pub">
<p class="list-post-title" align="left">
<a class="name" href="{{ site.baseurl }}{{ pub.url }}"> <dl style="font-size:0.7rem;"><li> 
{{ pub.title }}<br>{{ pub.author }}<br>{{ pub.venue }}</li></dl></a><a href="{{ pub.paperurl }}">[Paper URL]</a>
</p>
</div>
{% endif %}
{% endfor %}
</div>

{% endif %}

<hr>
{% endfor %}
