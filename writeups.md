---
layout: default
---

<div class="posts">
  <ul>
 {% for post in site.posts %}
 <li style="margin-bottom: 30px;">

  <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>

  <div class="entry">
    {{ post.excerpt }}
  </div>

  <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
 </li>
 {% endfor %}
  </ul>
</div>
