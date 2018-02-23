---
layout: default
title: "标签"
description: "哈哈，你找到了我的文章基因库"  
---

<div>
	<ul class="nav nav-tabs" role="tablist">
		{% for key,tag in site.tags %}
		{% if key eq 0 %}
		<li role="presentation" class="active"><a href="#{{ tag[0] }}" aria-controls="{{ tag[0] }}" role="tab" data-toggle="tab">{{ tag[0] }}</a></li>
		{% else %}
		<li role="presentation"><a href="#{{ tag[0] }}" aria-controls="{{ tag[0] }}" role="tab" data-toggle="tab">{{ tag[0] }}</a></li>
		{% endif %}
		{% endfor %}
	</ul>

  <div class="tab-content">
  	{% for key,tag in site.tags %}
  		{% if key eq 0 %}
	  	<div role="tabpanel" class="tab-pane active" id="{{ tag[0] }}">
	  	{% else %}
	  	<div role="tabpanel" class="tab-pane" id="{{ tag[0] }}">
	  	{% endif %}
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
  

