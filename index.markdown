---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Click the event name to see the full detail
order: 1
---
<h1>
This week 
</h1>
<!-- {{ site.posts[0].url }} -->
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | prepend : site.baseurl | prepend: site.url }}">{{ post.title }}</a>
      <!-- {{ post.date }}
      {{ post.url | prepend: site.baseurl | prepend: site.url }} -->
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>
<h1>
Up-coming 
</h1>

<h1>
Past
</h1>