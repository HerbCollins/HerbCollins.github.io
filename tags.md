---
layout: new
title: "Tags"
description: ""
---
<div class="container">
	<div class="row">
		<div class="col-xs-12 col-md-8">
		  	{% for tag in site.tags %}
			  	<div id="{{ tag[0] }}">
					{% for post in tag[1] %}
						<h4>
							<a href="{{ post.url }}">
								{{ post.title }}
							</a>
						</h4>
						<p class="text-right text-sm">-- {{ post.date | date: "%Y-%m-%d" }}</p>
						<hr>
					{% endfor %}
				</div>
			{% endfor %}
		</div>
		<div class="col-md-4">
			<div class="list-group">
				{% for tag in site.tags %}
				  	<a href="#{{ tag[0] }}" class="list-group-item">
				    	{{ tag[0] }} 
				    	<span class="badge">{{ tag[1].size }}</span>
				  	</a>
			  	{% endfor %}
			</div>
		</div>
	</div>
</div>

