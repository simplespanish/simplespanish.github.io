---
layout: default
title: Simple Spanish Blog
permalink: /blog/
cssFiles: 
- blog.css
---

{{ total_pages }}
{{ total_posts }}

<div class="posts container">
	<div class="row">
		{% for post in site.posts %}
		<div class="col-sm-8 col-sm-offset-2 col-xs-10 col-xs-offset-1">
			<h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>
			<div class="entry">
				{% if post.image %}
				<img src="{{ site.baseurl}}/images/{{ post.image }}" class="img-thumbnail pull-left entryImg" alt="Responsive image">
				<!-- <div class="img-thumbnail entryImg" src="{{ site.baseurl}}/images/{{ post.image }}"></div> -->
				{% endif %}
				{{ post.description }}
			</div>
			<a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
		</div>
		{% endfor %}
	</div>



	<nav class="">
	  <ul class="pagination center-block">
		  <li><a href="#"><span aria-hidden="true">&laquo;</span><span class="sr-only">Previous</span></a></li>
	  	{% for i in (1..page.total_posts) %}
		    
		    <li><a href="#">{{ i }}</a></li>
	    {% endfor %}
	    <li><a href="#"><span aria-hidden="true">&raquo;</span><span class="sr-only">Next</span></a></li>
	  </ul>
	</nav>
</div>