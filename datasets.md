---
title: All Datasets
permalink: /datasets/
---

<table class="table table-responsive table-striped">
<thead>
<tr>
<th>Name</th>
<th>Source</th>
<th>License</th>
<th>DOI</th>
</tr>
</thead>
<tbody>
{% assign sorted = site.pages | sort: 'url' %}
{% for page in sorted %}
{% if page.type == "dataset" %}
<tr>
  <td><a href="{{ page.url }}">{{ page.title }}</a></td>
  <td><a href="{{ site.baseurl}}/{{ page.source }}/">{{ page.source }}</a></td>
  <td>{{ page.license }}</td>
  <td><a href="http://dx.doi.org/{{ page.doi }}">{{ page.doi }}</a></td>
</tr>
{% endif %}
{% endfor %}
</tbody>
</table>
