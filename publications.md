---
title: Publications
permalink: /publications/
---

{%- assign pub_sorted = site.publications | sort: 'date' -%}
{%- assign pub_array = "pub|standard" | split: "|" -%}
{%- assign year_array = "2018|2017|2016|2015|2014|2013|2012|2011|2010|2009|2008|2007|2006|2005" | split: "|" -%}

{%- for item in pub_array -%}
{%- if item == 'pub' -%}
<h1>Publications</h1>
{%- elsif item == 'standard' -%}
<h1>Standards, White Papers, Technical Reports</h1>
{%- endif -%}

{%- if item == 'pub' -%}
{%- for year in year_array -%}
{%- if year == '2018' -%}
<h2 class="pub-year">2018</h2>
{%- elsif year == '2017' -%}
<h2 class="pub-year">2017</h2>
{%- elsif year == '2016' -%}
<h2 class="pub-year">2016</h2>
{%- elsif year == '2015' -%}
<h2 class="pub-year">2015</h2>
{%- elsif year == '2014' -%}
<h2 class="pub-year">2014</h2>
{%- elsif year == '2013' -%}
<h2 class="pub-year">2013</h2>
{%- elsif year == '2012' -%}
<h2 class="pub-year">2012</h2>
{%- elsif year == '2011' -%}
<h2 class="pub-year">2011</h2>
{%- elsif year == '2010' -%}
<h2 class="pub-year">2010</h2>
{%- elsif year == '2009' -%}
<h2 class="pub-year">2009</h2>
{%- elsif year == '2008' -%}
<h2 class="pub-year">2008</h2>
{%- elsif year == '2007' -%}
<h2 class="pub-year">2007</h2>
{%- elsif year == '2006' -%}
<h2 class="pub-year">2006</h2>
{%- elsif year == '2005' -%}
<h2 class="pub-year">2005</h2>
{%- endif -%}

{%- for pub in pub_sorted reversed -%}
{%- assign date = pub.date | date_to_long_string -%}
{%- if pub.type contains item and date contains year -%}
<div class="pub-page-grid-container">
<p class="pub-list-ref">
<b>{{ pub.title }}</b>. {{ pub.author }}. <i>{{ pub.venue }}</i>.
</p>
<p class="pub-list-ref-links">
{%- if pub.abstract -%}<a href="{{ site.baseurl }}{{ pub.url }}"><i class="fas fa-align-justify"></i> Abstract</a>{%- endif -%}
{%- if pub.paperurl -%}<span><a href="{{ pub.paperurl }}"><i class="fas fa-file-alt"></i> Paper</a></span>{%- endif -%}
</p>
</div>
{%- endif -%}
{%- endfor -%}
{%- endfor -%}

{%- else -%}
{%- for pub in pub_sorted reversed -%}
{%- if pub.type contains item -%}
<div class="pub-page-grid-container">
<p class="pub-list-ref">
<b>{{ pub.title }}</b>. {{ pub.author }}. {% if pub.venue %}<i>{{ pub.venue }}</i>.{% endif %}
</p>
<p class="pub-list-ref-links">
{%- if pub.abstract -%}<a href="{{ site.baseurl }}{{ pub.url }}"><i class="fas fa-align-justify"></i> Abstract</a>{%- endif -%}
{%- if pub.paperurl -%}<a href="{{ pub.paperurl }}"><i class="fas fa-file-alt"></i> Paper</a>{%- endif -%}
</p>
</div>
{%- endif -%}
{%- endfor -%}
{%- endif -%}
{%- endfor -%}
