---
title: All Posts - Simple List
permalink: "/all-posts/"
layout: page
inmenu: 1
---


[Switch to detailed view](/all-posts-detailed)


<div class='homepage-recent-blurbs main-unit'>


	<div class='page-all-posts'>
		<div class='all-posts' >

	      {% for post in site.posts %}

			<div class='post'>
				<span class='date'>
					{{ post.date  | date: "%d %b %Y" }}
				</span>
				<span class='title'>
					 <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
				</span>
				<span class='categories'>
					{{ post.categories }}
				</span>

			</div>

	      {% endfor %}


		</div>
	</div>
</div>
