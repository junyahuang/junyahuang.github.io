---
layout: page
title: "Brain"
description: "逐渐绽放的脑洞"
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
  </h3>
 
  <li class="listing-item">
   <h4> <time datetime="{{ post.date | date:"%m-%d" }}">{{ post.date | date:"%m-%d" }}</time>
    &nbsp;&nbsp;&nbsp;&nbsp;
    <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
    </h4>
  </li>
{% endfor %}
</ul>


