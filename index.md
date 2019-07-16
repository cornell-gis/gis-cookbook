---
layout: default
title: Cornell GIS Cookbook
---

<p>Welcome to the Cornell Library GIS Cookbook!  Here we share some of our favorite recipes for mapping and geospatial analysis using software like QGIS and ArcMap.</p>

<div id='qgis'>
  <h2>
    ![QGIS logo](https://user-images.githubusercontent.com/3355358/61306269-4b43c900-a7ba-11e9-9e19-aa185d3b6e7c.png)
    QGIS
  </h2>
  <ul>
    {% for p in site.pages %}
      {% if p.path contains 'qgis' %}
        <li><a href="/gis-cookbook/{{p.path | remove: '.md'}}">{{p.title}}</a></li>
      {% endif %}
    {% endfor %}
  </ul>
</div>

<div id='arcmap'>
  <h2>ArcMap</h2>
  <ul>
    {% for p in site.pages %}
      {% if p.path contains 'arcmap' %}
        <li><a href="/gis-cookbook/{{p.path | remove: '.md'}}">{{p.title}}</a></li>
      {% endif %}
    {% endfor %}
  </ul>
</div>
