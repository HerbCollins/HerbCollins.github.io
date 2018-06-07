---
layout: page
title:"Articles"
description: "个人博客"
---

<div class="container">
		<div class="row">
			<div class="col-xs-12 col-md-8 col-lg-9">
				<div class="page-header text-center">
					<p class="page-title">The Lastest Article</p>
				</div>
				<div class="panel">
					<div class="panel-body">
						{% for post in paginator.posts %}
							<h1><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h1>
							<p>{{ post.content }}</p>
							<div class="article-attrs">
								<span>
									<i class="fa fa-fw fa-calendar"></i> {{ post.date | date: "%Y-%m-%d" }}
								</span>
								<span><i class="fa fa-fw fa-tags"></i> 
									{% for tag in post.tags %}
										<span>{{ tag }}</span>
									{% endfor %}
								</span>
							</div>
						{% endfor %}
					</div>
				</div>

				<!-- Pager -->
				{% if paginator.total_pages > 1 %}
				<ul class="pager">
				    {% if paginator.previous_page %}
				    <li class="previous">
				        <a href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">上一页</a>
				    </li>
				    {% endif %}
				    {% if paginator.next_page %}
				    <li class="next">
				        <a href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">下一页</a>
				    </li>
				    {% endif %}
				</ul>
				{% endif %}
			</div>
			<div class="col-xs-12 col-md-4 col-lg-3">
				
			</div>
		</div>
	</div>