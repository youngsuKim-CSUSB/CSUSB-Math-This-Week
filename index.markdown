---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
# title: 
order: 1
---
<!-- {{ site.time | date: '%y' }} -->
{% capture systemThisWeek %}{{'now' | date: '%W'}}{% endcapture %}
<h2> This week; today is {{ 'now' | date: "%a, %D" }} </h2> 
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

<h2>
Up-coming events
</h2>
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

<h2>
Past events
</h2>
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