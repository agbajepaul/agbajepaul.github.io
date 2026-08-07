---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% include base_path %}

{% if site.author.googlescholar %}
<div class="notice--primary" markdown="1">
#### Looking for the most current list?

Everything below is also on <a href="{{ site.author.googlescholar }}">my Google Scholar profile</a>.
</div>
{% endif %}

{% assign journal_pubs = site.data.publications | where: "type", "journal" %}
{% assign conference_pubs = site.data.publications | where: "type", "conference" %}
{% assign preprint_pubs = site.data.publications | where: "type", "preprint" %}

<h2 class="archive__subtitle">Journal Articles</h2>
<div class="pub-list">
  {% for pub in journal_pubs %}{% include publication-item.html pub=pub %}{% endfor %}
</div>

<h2 class="archive__subtitle">Conference &amp; Workshop Proceedings</h2>
<div class="pub-list">
  {% for pub in conference_pubs %}{% include publication-item.html pub=pub %}{% endfor %}
</div>

{% if preprint_pubs.size > 0 %}
<h2 class="archive__subtitle">Preprints</h2>
<div class="pub-list">
  {% for pub in preprint_pubs %}{% include publication-item.html pub=pub %}{% endfor %}
</div>
{% endif %}
