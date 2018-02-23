---
layout: default
title: "标签 | Tags"
description: "哈哈，你找到了我的文章基因库"  
---


<div id='tag_cloud'>
{% for tag in site.tags %}
<a href="#{{ tag[0] }}" class="label label-primary" title="{{ tag[0] }}" rel="{{ tag[1].size }}">{{ tag[0] }}</a>
{% endfor %}
</div>

<ul class="listing">
{% for tag in site.tags %}
  <li class="listing-seperator" id="{{ tag[0] }}">{{ tag[0] }}</li>
{% for post in tag[1] %}
  <li class="listing-item">
  <span class="tag-time"><time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time></span>
  <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
  </li>
{% endfor %}
{% endfor %}
</ul>
