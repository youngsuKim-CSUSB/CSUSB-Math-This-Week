---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
# title: 
order: 1
---
<!-- {{ site.time | date: '%y' }} -->
{% capture systemThisWeek %}{{'now' | date: '%W'}}{% endcapture %}
# This week; today is {{ 'now' | date: "%a, %D" }}
<!-- {{ site.posts[0].url }} -->
<ul>
  {% for post in site.posts %}
  {% capture postWeek %}{{post.date | date: '%W'}}{% endcapture %}
  {% if postWeek == systemThisWeek %}
      <li> 
      <a href="{{ post.url | prepend : site.baseurl | prepend: site.url }}">{{ post.title }}</a>
      {{ post.date | date: 'on %a, %D at %I %P' }} 
      {{ post.excerpt }}
      </li>
  {% endif %}
  {% endfor %}
</ul>

## Up-coming events
<ul>
  {% for post in site.posts %}
  {% capture postWeek %}{{post.date | date: '%W'}}{% endcapture %}
  {% if postWeek > systemThisWeek %}
      <li> 
      <a href="{{ post.url | prepend : site.baseurl | prepend: site.url }}">{{ post.title }}</a>
      {{ post.date | date: 'on %a, %D at %I %P' }} 
      {{ post.excerpt }}
      </li>
  {% endif %}
  {% endfor %}
</ul>

## Past events
<ul>
  {% for post in site.posts %}
  {% capture postWeek %}{{post.date | date: '%W'}}{% endcapture %}
  {% if postWeek < systemThisWeek %}
      <li> 
      <a href="{{ post.url | prepend : site.baseurl | prepend: site.url }}">{{ post.title }}</a>
      {{ post.date | date: 'on %a, %D at %I %P' }} 
      {{ post.excerpt }}
      </li>
  {% endif %}
  {% endfor %}
</ul>

## Happening this semester
