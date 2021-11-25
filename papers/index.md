---
layout: default
regenerate: true
---

<div class="posts">
  <ul>
      {% assign papers = site.papers | sort: "readings" | reverse %}
      {% for paper in papers %}
          <li>{{ paper.title }} [<a href="{{ site.baseurl }}{{ paper.url }}">{{ paper.slug }}</a>]</li>
      {% endfor %}
  </ul>
</div>

