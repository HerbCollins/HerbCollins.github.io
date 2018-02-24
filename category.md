---
layout: default
title: "归档"
description: "哈哈，你找到了我的文章基因库"
---
<div class="col-md-2">
	<ul class="nav nav-tabs side-nav" role="tablist">
		{% for tag in site.tags %}
		
		<li role="presentation"><a href="#{{ tag[0] }}" aria-controls="{{ tag[0] }}" role="tab" data-toggle="tab">{{ tag[0] }}</a></li>
		
		{% endfor %}
	</ul>
</div>
<div class="col-md-10">
  	 <div class="tab-content">
  	{% for tag in site.tags %}
  		
	  	<div role="tabpanel" class="tab-pane" id="{{ tag[0] }}">
	  		<ul class="list-group">
			{% for post in tag[1] %}
			  <li class="listing-item list-item">
			  <span class="tag-time"><time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time></span>
			  <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
			  </li>
			{% endfor %}
			</ul>
		</div>
	{% endfor %}
  
</div>
{% endfor %}