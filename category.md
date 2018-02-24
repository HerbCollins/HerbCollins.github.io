---
layout: default
title: "归档"
description: "哈哈，你找到了我的文章基因库"
---
<div class="col-md-2">
	<ul class="nav nav-tabs" role="tablist">
		{% for cate in site.category %}
		
		<li role="presentation"><a href="#{{ cate[0] }}" aria-controls="{{ cate[0] }}" role="tab" data-toggle="tab">{{ cate[0] }}</a></li>
		
		{% endfor %}
	</ul>
</div>
{% for post in paginator.posts %}
<div class="col-md-12">
	<a href="{{ post.url | prepend: site.baseurl }}" class="panel article-li">
		<div class="panel-body">
			<h2>{{ post.title }} 
				<small><i>{{ post.date | date: "%Y-%m-%d" }} By {% if post.author %}{{ post.author }}{% else %}{{ site.title }}{% endif %}</i></small>
				<span class="pull-right" style="font-size: 14px;">
				{% for tag in post.tags %}
					<span class="label label-info">
						<i class="fa fa-fw fa-circle-thin"></i> {{ tag }}
					</span>
				{% endfor %}
				</span>
			</h2>
			<p>{{ post.content | strip_html | truncate:150 }}</p>
		</div>
	</a>
</div>
{% endfor %}