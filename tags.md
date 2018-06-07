---
layout: default
title: "Tags"
description: ""
---
<div class="col-md-2">
	<ul class="nav nav-tabs side-nav" role="tablist">
		{% for tag in site.tags %}
		
		<li role="presentation"><a href="#{{ tag[0] }}" aria-controls="{{ tag[0] }}" role="tab" data-toggle="tab">{{ tag[0] }}</a></li>
		
		{% endfor %}
	</ul>
</div>
<div class="col-md-10 tab-content">
  	{% for tag in site.tags %}
	  	<div role="tabpanel" class="tab-pane" id="{{ tag[0] }}">
			{% for post in tag[1] %}
				<a href="{{ post.url  }}">
						<h4><span>{{ post.date | date: "%Y-%m-%d" }}</span>-{{ post.title }}</h4>
				</a>
			{% endfor %}
		</div>
	{% endfor %}
  
</div>