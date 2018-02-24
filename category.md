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
  	{% for tag in site.tags %}
  		
	  	<div role="tabpanel" class="tab-pane" id="{{ tag[0] }}">
	  	
			{% for post in tag[1] %}

				<a href="{{ post.url  }}" class="panel article-li">
					<div class="panel-body">
						<h2>{{ post.title }} 
							<small>
								<i>{{ post.date | date: "%Y-%m-%d" }} By 
								{% if post.author %}
								{{ post.author }}
								{% else %}
									{{ site.title }}
							{% endif %}
							</i></small>
						</h2>
					</div>
				</a>
			{% endfor %}
		</div>
	{% endfor %}
  
</div>