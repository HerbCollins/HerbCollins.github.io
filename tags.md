---
layout: default
title: "标签"
description: "哈哈，你找到了我的文章基因库"  
---

<div>
	<ul class="nav nav-tabs" role="tablist">
		{% for tag in site.tags %}
		<li role="presentation"><a href="#{{ tag[0] }}" aria-controls="{{ tag[0] }}" role="tab" data-toggle="tab">{{ tag[0] }}</a></li>
		{% endfor %}
	</ul>

  <div class="tab-content">
  	{% for tag in site.tags %}
	  	<div role="tabpanel" class="tab-pane" id="{{ tag[0] }}">
			{% for post in tag[1] %}
			  <li class="listing-item">
			  <span class="tag-time"><time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time></span>
			  <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
			  </li>
			{% endfor %}
		</div>
	{% endfor %}
  </div>
</div>
  

