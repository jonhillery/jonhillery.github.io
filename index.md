---
layout: page
title: "Home"
class: home
---

# Hi, I'm Jon Hillery

<div class="columns" markdown="1">

<div class="intro" markdown="1">
I'm a PhD student in the [UCLA Department of Mathematics](https://ww3.math.ucla.edu/), interested in representation theory. I was previously a student at UC Berkeley and Cambridge University. More info about me is in my [CV]({{ "/cv/" | relative_url }}).
</div>

<div class="me" markdown="1">
<picture>
  <source srcset='/images/jon_sfmoma.webp' type='image/webp' />
  <img
    src='/images/jon_sfmoma.jpg'
    alt='Dominik Moritz'>
</picture>

{:.no-list}
* <a href="mailto:{{ site.email }}">{{ site.email }}</a>
* MS 2350
</div>

</div>

For Fall 2024, I'm a TA for Math 33A Linear Algebra and Applications. My office hours are Thursdays 10-11 in MS 2350. <a href=assets/Fall_2024_MATH33A_Worksheets.pdf>Worksheet 1</a>

## Featured <a href="{{ "/projects/" | relative_url }}">Projects</a>

<div class="featured-projects">
  {% assign sorted_projects = site.data.projects | sort: 'highlight' %}
  {% for project in sorted_projects %}
    {% if project.highlight %}
      {% include project.html project=project %}
    {% endif %}
  {% endfor %}
</div>

<a href="{{ "/projects/" | relative_url }}" class="button">
  <i class="fas fa-chevron-circle-right"></i>
  Show More Projects
</a>

## Featured <a href="{{ "/publications/" | relative_url }}">Publications</a>

<div class="featured-publications">
  {% assign sorted_publications = site.publications | sort: 'year' | reverse %}
  {% for pub in sorted_publications %}
    {% if pub.highlight %}
      <a href="{{ pub.pdf }}" class="publication">
        <strong>{{ pub.title }}</strong>
        <span class="authors">{% for author in pub.authors %}{{ author }}{% unless forloop.last %}, {% endunless %}{% endfor %}</span>.
        <i>{% if pub.venue %}{{ pub.venue }}, {% endif %}{{ pub.year }}</i>.
        {% for award in pub.awards %}<br/><span class="award"><i class="fas fa-{% if award == "Best Paper Award" %}trophy{% else %}award{% endif %}" aria-hidden="true"></i> {{ award }}</span>{% endfor %}
      </a>
    {% endif %}
  {% endfor %}
</div>

<a href="{{ "/publications/" | relative_url }}" class="button">
  <i class="fas fa-chevron-circle-right"></i>
  Show All Publications
</a>
