---
layout: page
title: Post Index
sitemap: false
paginate:
  enabled: true
  collection:   posts
  per_page:     4             # maximum number of items per page
  limit:        5              # Maximum number of pages to paginate (false for unlimited)
  permalink:    /blog/page:num/     # pagination path (relative to template page)
  title_suffix: " - page :num" # Append to template's page title
  reversed:     false          # Reverse the order of the documents
  trail:
    before: 2 # The number of links before the current page
    after: 2  # The number of links after the current page
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
