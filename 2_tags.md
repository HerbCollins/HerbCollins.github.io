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
					<div class="panel panel-info">
						<div class="panel-heading">
							<span>
								{{ tag[0] }} 
							</span>
						</div>
						<div class="panel-body">
							{% for post in tag[1] %}
							<p>
								<a href="{{ post.url }}">
								<h4 style="display: inline-block;">{{ post.title }}</h4>
								</a>
								<span class="pull-right text-sm">-- {{ post.date | date: "%Y-%m-%d" }}</span>
							</p>
							<hr>
							{% endfor %}
						</div>
					</div>
				</div>
			{% endfor %}
		</div>
		<div class="col-md-4">
			<div class="list-group">
				{% for tag in site.tags %}
				  	<a href="#{{ tag[0] }}" class="list-group-item">
				    	{{ tag[0] }} 
				    	<span class="label label-info pull-right">{{ tag[1].size }}</span>
				  	</a>
			  	{% endfor %}
			</div>
		</div>
	</div>
</div>

