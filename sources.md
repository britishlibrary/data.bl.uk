---
title: All Sources
permalink: /sources/
---

<table class="table table-responsive table-striped">
<thead>
<tr>
<th>Name</th>
<th>Datasets</th>
<th>DOI</th>
</tr>
</thead>
<tbody>
{% assign sorted = site.pages | sort: 'url' %}
{% for page in sorted %}
{% if page.type == "source" %}
<tr>
  <td><a href="{{ page.url }}">{{ page.title }}</a></td>
  <td>
  {% for spage in sorted %}
  {% if spage.type == "dataset" and spage.source == page.id %}
  <a href="{{ spage.url }}/">{{ spage.title }}</a><br/>
  {% endif %}
  {% endfor %}
  </td>
  <td><a href="http://dx.doi.org/{{ page.doi }}">{{ page.doi }}</a></td>
</tr>
{% endif %}
{% endfor %}
</tbody>
</table>
