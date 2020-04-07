---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Blog
nav_order: 1
description: "This blog is the place where I share my experience and knowledge I have obtained in time. You can find posts related to technology, entrepreneurship and agriculture."
permalink: /
pagination: 
  enabled: true
  total_posts: 10
  page_path: /
---

<h1 class="fs-9">Experience != Age</h1>
<p class="fs-6 fw-300">
Wisdom is knowledge through experience, not age. Just because someone is older than you, doesn’t mean they’re wiser than you are. And for those who assume otherwise, you’ve already made clear the extent of your wisdom.
</p>
<p>
<a class="btn btn-primary fs-5 mb-4 mb-md-0 mr-2" href="#blogs">Continue Reading</a>
<a class="btn fs-5 mb-4 mb-md-0" href="https://jamespj.com" target="_blank">My Portfolio</a>
</p>

<h2 id="blogs">Blogs</h2>

{% assign posts_count = paginator.posts | size %}
<div class="home">
  {% if posts_count > 0 %}
    <div class="posts">
      {% for post in paginator.posts %}
        <div class="post py3">
          <p class="post-meta">
	    {% if site.date_format %}
	      {{ post.date | date: site.date_format }}
	    {% else %}
	      {{ post.date | date: "%b %-d, %Y" }}
	    {% endif %}
	  </p>
          <a href="{{ post.url | relative_url }}" class="post-link"><h3 class="h1 post-title">{{ post.title }}</h3></a>
          <span class="post-summary">
            {% if post.summary %}
              {{ post.summary }}
            {% else %}
              {{ post.excerpt }}
            {% endif %}
          </span>
        </div>
      {% endfor %}
    </div>

    {% include pagination.html %}
  {% else %}
    <h1 class='center'>{{ site.text.index.coming_soon }}</h1>
  {% endif %}
</div>