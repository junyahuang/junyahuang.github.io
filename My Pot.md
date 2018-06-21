---
layout: page
title: "MyPot"
description: "我的锅能有这么大"
header-img: "img/headline6.jpg"
---


 <h3><ul class="listing">
{% for post in site.posts %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
  {% if year != y %}
    {% assign year = y %}
    <br /><br /><li class="listing-seperator">{{ y }}<br /><br />
</li>
  {% endif %}
 
 
  <li class="listing-item">
   <h4> <time datetime="{{ post.date | date:"%m-%d" }}">{{ post.date | date:"%m-%d" }}</time>
    &nbsp;&nbsp;&nbsp;&nbsp;
    <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
    </h4>
  </li>
{% endfor %}
</ul> </h3>


