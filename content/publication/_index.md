---
title: Research

# View.
#   1 = List
#   2 = Compact
#   3 = Card
#   4 = Citation
view: 4

# Optional header image (relative to `static/img/` folder).
header:
  caption: ""
  image: ""
---

<h3><a href="/files/nowlin-cv.pdf">Curriculum Vitae</a></h3> 

<div class ="category-name">
<h3>Book</h3>
</div>
{% assign bookByYear = site.research | where: "publication_types", "5" | group_by_exp:"date"  %}
{% for year in bookByYear reversed%}
<div class="is-row">
  <div class="is-col is-10 paperlist">
    {{year.name}}
  </div>
  <div class="is-col is-90 paperlist">
    <ul>
      {% for paper in year.items %}
      <li> {% if paper.url %} 
    {{paper.author}}. <em>{{paper.title}}</em>. {% if paper.publisher %} <b>{{paper.publisher}}</b> <a href="{{paper.url}}" class="boxlink">book site</a> {% endif %}
    {% else %}
    {{paper.title}} 
    {% endif %} 
      </li>
      {% endfor %}
    </ul>
  </div>
</div>
{% endfor %}



