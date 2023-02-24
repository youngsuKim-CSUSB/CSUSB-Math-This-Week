---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
# title: 
order: 1
---
{% capture systemYear %}{{'now' | date: '%y'}}{% endcapture %}
{% capture systemThisWeek %}{{'now' | date: '%W'}}{% endcapture %}
## **This week** <font size="2"> today is {{ 'now' | date: "%a %D" }} </font> 
<ul>
  {% for post in site.posts reversed %}
  {% capture postWeek %}{{post.date | date: '%W'}}{% endcapture %}
  {% capture postYear %}{{post.date | date: '%y'}}{% endcapture %}
  {% if postYear == systemYear %}
  {% if postWeek == systemThisWeek %}
      <li> 
      <font size="4">
      <a href="{{ post.url | prepend : site.baseurl | prepend: site.url }}">{{ post.title }}</a>
      </font>
      {% if postMinutes == '00' %}
        {{ post.date | date: 'on %a %D at %-I %P' }} 
      {% else %}
        {{ post.date | date: 'on %a %D at %-I:%M %P' }} 
      {% endif %}      
      {{ post.excerpt }}
      </li>
  {% endif %}
  {% endif %}
  {% endfor %}
</ul>


### __Up-coming events__
<ul>
  {% for post in site.posts reversed %}
  {% capture postYear %}{{post.date | date: '%y'}}{% endcapture %}
  {% capture postWeek %}{{post.date | date: '%W'}}{% endcapture %}
  {% if postYear == systemYear %}
    {% if postWeek > systemThisWeek %}
      <li> 
      <!-- <font size="4"> -->
      <a href="{{ post.url | prepend : site.baseurl | prepend: site.url }}">{{ post.title }}</a>
      <!-- </font> -->
      {{ post.date | date: 'on %a %D'  }} 
      {{ post.excerpt }}
      </li>
    {% endif %}
  {% endif %}
  {% endfor %}
</ul>


<!-- ### **Spring 2022 News**
  
- F2022 Advising Begins on March 21st. The 2022-2026 tentative course listing is available on the [webpage](https://www.csusb.edu/mathematics/undergraduate/advising) (Program and Course Resources, Item 7).
- CSUSB Putnam Team ranked 291/427.  -->

#### **Past events**
<ul>
  {% for post in site.posts %}
  {% capture postWeek %}{{post.date | date: '%W'}}{% endcapture %}
  {% if postYear == systemYear %}
    {% if postWeek < systemThisWeek %}
      <li> 
      <!-- <font size="4"> -->
      <a href="{{ post.url | prepend : site.baseurl | prepend: site.url }}">{{ post.title }}</a>
      <!-- </font> -->
      {{ post.date | date: 'on %a %D'  }} 
      <!-- {{ post.excerpt }} -->
      </li>
    {% endif %}
  {% endif %}
  {% endfor %}
</ul>

#### **In 2022**
<ul>
  {% for post in site.posts %}
  {% capture postYear %}{{post.date | date: '%y'}}{% endcapture %}
    {% if postYear < systemYear %}
        <li> 
        <a href="{{ post.url | prepend : site.baseurl | prepend: site.url }}">{{ post.title }}</a>
        {{ post.date | date: 'on %a %D'  }} 
        {{ postYear }}
        </li>
    {% endif %}
  {% endfor %}
</ul>

<!-- ## SageMath -->

<!-- * Thanks to Pedro, if you want to try out [Sage](https://www.sagemath.org/), use your CSUSB credentials to login [myhorizon.csusb.edu](https://myhorizon.csusb.edu); for questions and comments contact Youngsu Kim.  -->
<!-- * If you need high-performance computing, please consider [HPC at CSUSB](https://www.csusb.edu/academic-technologies-innovation/xreal-lab-and-high-performance-computing/high-performance-0). -->

<!-- ---
layout: page
title: Google Forms (Under construction)
permalink: /Google-Forms/
tag: Google form
---
This page will include a Google form link to submit events.  -->

<!-- [jekyll][jekyll-organization]
[jekyll](https://github.com/jekyll/jekyll) -->