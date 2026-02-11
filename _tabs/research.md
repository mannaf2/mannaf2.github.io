---
# the default layout is 'page'
layout: page
icon: fas fa-flask-vial
math: true
permalink: /research/
order: 5
---

 
<!-- ---
layout: page
title: Research
permalink: /research/
---

# Publications

--- -->

## ⭐ Selected Articles

{% for pub in site.data.publications.articles %}
  {% if pub.featured %}
- **{{ pub.title }}**  
  {{ pub.authors }}  
  *{{ pub.venue }}*, {{ pub.year }}  
  {% if pub.pdf %}[PDF]({{ pub.pdf }}){% endif %}
  {% if pub.doi %} | [DOI]({{ pub.doi }}){% endif %}
  {% if pub.arxiv %} | [arXiv]({{ pub.arxiv }}){% endif %}
  {% endif %}
{% endfor %}

---

## 📝 Journal Articles  

{% assign articles = site.data.publications.articles | sort: "year" | reverse %}
{% assign counter = 0 %}

{% for pub in articles %}
  {% assign counter = counter | plus: 1 %}

**{{ counter }}.** **{{ pub.title }}**  
{{ pub.authors }}  
*{{ pub.venue }}* {% if pub.volume %}, Vol. {{ pub.volume }}{% endif %} {% if pub.issue %}, No. {{ pub.issue }}{% endif %}{% if pub.pages %}, pp. {{ pub.pages }}{% endif %}({{ pub.year }})
{% if pub.doi %} | [DOI]({{ pub.doi }}){% endif %}
{% if pub.pdf %} | [PDF]({{ pub.pdf }}){% endif %}
{% if pub.arxiv %} | [arXiv]({{ pub.arxiv }}){% endif %}

<br><br>

{% endfor %}


---

## 🎤 Conferences  

{% assign confs = site.data.publications.conferences | sort: "year" | reverse %}
{% assign counterconfs = 0 %}
{% for pub in confs %}
{% assign counterconfs = counterconfs | plus: 1 %}
**{{ counterconfs }}.** **{{ pub.title }}**  
  {{ pub.authors }}  
  *{{ pub.venue }}*, {{ pub.year }}  
  {% if pub.pdf %}[PDF]({{ pub.pdf }}){% endif %}
{% endfor %}

---

## 📄 Preprints

{% assign preprints = site.data.publications.preprints | sort: "year" | reverse %}
{% for pub in preprints %}
- **{{ pub.title }}**  
  {{ pub.authors }}  
  {{ pub.year }}  
  {% if pub.arxiv %}[arXiv]({{ pub.arxiv }}){% endif %}
{% endfor %}

---

## 💻 Projects

{% for pub in site.data.publications.projects %}
- **{{ pub.title }}** ({{ pub.year }})  
  {{ pub.description }}  
  {% if pub.link %}[Repository]({{ pub.link }}){% endif %}
{% endfor %}

---

## 🎓 Others

{% for pub in site.data.publications.others %}
- **{{ pub.title }}** ({{ pub.year }})
{% endfor %}

