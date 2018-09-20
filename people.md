---
title: People
permalink: /people/
---

{% assign people_sorted = (site.people | sort: 'joined') %}
{% assign people_array = "pi|researcher|phd|ms|undergrad|visiting" | split: "|" %}

{% for item in people_array %}

<div class="pos_header">
 {% if item == 'pi' %}
<h3>Principal Investigator</h3>
 {% elsif item == 'researcher' %}
<h3>Researchers</h3>
 {% elsif item == 'phd' %}
<h3>Graduate (PhD) Students</h3>
 {% elsif item == 'ms' %}
<h3>Graduate (MS) Students</h3>
 {% elsif item == 'undergrad' %}
<h3>Undergraduate Students</h3>
 {% elsif item == 'visiting' %}
<h3>Visiting Scholars</h3>
{% endif %}
</div>

<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains item %}
    <div class="list-item-people">
      <p class="list-post-title">
        {% if profile.avatar %}
        <a href="{{ site.baseurl }}{{ profile.url }}"><img width="200" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
        {% else %}
        <a href="{{ site.baseurl }}{{ profile.url }}"><img width="200" src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg"></a>
        {% endif %}
        <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
      </p>
    </div>    
    {% endif %}
  {% endfor %}
</div>
<hr>
{% endfor %}

<h3>Alumni</h3>
<dl style="font-size:0.7rem;">
<li>Ming Tai Ha</li>
<li>Ole Weidner (LEGO, Denmark)</li>
<li>Franklin Bettencourt</li>
<li>Alessio Angius</li>
<li>Nivetha Balasamy</li>
<li>Antons Treikalis</li>
<li>Nikhil Shenoy</li>
<li>Suvigya Tripathi (Intel)</li>
<li>Dinesh Ganapathi (Avaya)</li>
<li>Vishal Shah</li>
<li>Anjani Bhargavi (Neuroscience, USC)</li>
<li>Abhinav Thota (Indiana University Research Technology Division)</li>
<li>Pradeep Mantha (Berkeley Labs, now Salesforce)</li>
<li>Sharath Maddineni (Google)</li>
<li>Chris Miceli</li>
<li>Michael Miceli</li>
<li>Hartmut Kaiser (Senior Research Scientist at Louisiana State University)</li>
<li>Ashley Zebrowski</li>
<li>Aikaterina Stamou (nowaPhD student in Zurich, after a brief stint in Industry)</li>
</dl>
