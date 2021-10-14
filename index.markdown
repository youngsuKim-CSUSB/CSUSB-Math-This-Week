---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
# title: 
order: 1
---
{% capture systemThisWeek %}{{'now' | date: '%W'}}{% endcapture %}
# This week <font size="2"> today is {{ 'now' | date: "%a, %D" }} </font> 
<!-- {{ site.posts[0].url }} -->
<ul>
  <!-- {% assign orderedpost = site.posts | reverse %} -->
  {% for post in site.posts reversed %}
  {% capture postWeek %}{{post.date | date: '%W'}}{% endcapture %}
  {% if postWeek == systemThisWeek %}
      <li> 
      <font size="4">
      <a href="{{ post.url | prepend : site.baseurl | prepend: site.url }}">{{ post.title }}</a>
      </font>
      {{ post.date | date: 'on %a, %-m/%-d at %-I %P' }} 
      {{ post.excerpt }}
      </li>
  {% endif %}
  {% endfor %}
</ul>

## Up-coming events
<ul>
  {% for post in site.posts reversed %}
  {% capture postWeek %}{{post.date | date: '%W'}}{% endcapture %}
  {% if postWeek > systemThisWeek %}
      <li> 
      <a href="{{ post.url | prepend : site.baseurl | prepend: site.url }}">{{ post.title }}</a>
      {{ post.date | date: 'on %a, %D at %-I %P' }} 
      {{ post.excerpt }}
      </li>
  {% endif %}
  {% endfor %}
</ul>

## Past events
<ul>
  {% for post in site.posts reversed %}
  {% capture postWeek %}{{post.date | date: '%W'}}{% endcapture %}
  {% if postWeek < systemThisWeek %}
      <li> 
      <a href="{{ post.url | prepend : site.baseurl | prepend: site.url }}">{{ post.title }}</a>
      {{ post.date | date: 'on %a, %D' }} 
      <!-- {{ post.excerpt }} -->
      </li>
  {% endif %}
  {% endfor %}
</ul>

## Happening this semester

* [Math Club](https://www.csusb.edu/mathematics/undergraduate/math-club); F2021 membership fee is waived.

<!-- http://alanwsmith.com/jekyll-liquid-date-formatting-examples -->