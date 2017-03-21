---
title: Post Index
layout: page
sitemap: false
paginate:
  enabled: true
  collection: posts
  per_page: 4
  limit: 5
  permalink: "/blog/page:num/"
  title_suffix: " - page :num"
  reversed: false
  trail:
    before: 2
    after: 2
---

Paginatorx


{{ site.time }}


<HR>
{% for posts in paginator.posts %}
<DIV>{{posts.title}}</DIV>
{% endfor %}
<HR>



{% if paginator.page_trail %}
  {% for trail in paginator.page_trail %}
    <li {% if page.url == trail.path %}class="selected"{% endif %}>
        <a href="{{ trail.path | prepend: site.baseurl }}" title="{{trail.title}}">{{ trail.num }}</a>
    </li>
  {% endfor %}
{% endif %}





{% if paginator.total_pages > 1 %}
<ul>
  {% if paginator.previous_page %}
  <li>
    <a href="{{ paginator.previous_page_path | prepend: site.baseurl }}">Newer</a>
  </li>
  {% endif %}
  {% if paginator.next_page %}
  <li>
    <a href="{{ paginator.next_page_path | prepend: site.baseurl }}">Older</a>
  </li>
  {% endif %}
</ul>
{% endif %}
