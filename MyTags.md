---
layout: page
title: "My Tags"
description: "标签好烦"  
header-img: "img/headline4.jpg"  
---




{% for tag in site.tags %}
<h4> <li style="font-size: {{ tag | first | size | times: 70 | divided_by: site.tags.size | plus: 70  }}%">
<a href="#{{ tag | first | slugize }}">
   {{ tag | first }}
    </a>
  </li> 

{% endfor %}
</h4>

<br />
<br />
<br />

<div id="archives">
{% for tag in site.tags %}
  <div class="archive-group">
    {% capture tag_name %}{{ tag | first }}{% endcapture %}
    <h3 id="#{{ tag_name | slugize }}">{{ tag_name }}</h3>
    <a name="{{ tag_name | slugize }}"></a>
    {% for post in site.tags[tag_name] %}
    <article class="archive-item">
      <h4><a href="{{ root_url }}{{ post.url }}">{{post.title}}</a></h4>
    </article>
    {% endfor %}
  </div>
{% endfor %}
</div>

