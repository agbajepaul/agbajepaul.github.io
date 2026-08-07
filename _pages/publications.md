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

{% assign all_pubs = site.data.publications %}
{% assign years = all_pubs | map: "year" | uniq | sort | reverse %}

{% for year in years %}
{% assign year_journal = all_pubs | where: "year", year | where: "type", "journal" %}
{% assign year_conference = all_pubs | where: "year", year | where: "type", "conference" %}
{% assign year_preprint = all_pubs | where: "year", year | where: "type", "preprint" %}
<h2 class="pub-year">{{ year }}</h2>
{% if year_journal.size > 0 %}
<h3 class="pub-subheading">Journal Articles</h3>
<div class="pub-list">
{% for pub in year_journal %}{% include publication-item.html pub=pub %}{% endfor %}
</div>
{% endif %}
{% if year_conference.size > 0 %}
<h3 class="pub-subheading">Conference &amp; Workshop Proceedings</h3>
<div class="pub-list">
{% for pub in year_conference %}{% include publication-item.html pub=pub %}{% endfor %}
</div>
{% endif %}
{% if year_preprint.size > 0 %}
<h3 class="pub-subheading">Preprints</h3>
<div class="pub-list">
{% for pub in year_preprint %}{% include publication-item.html pub=pub %}{% endfor %}
</div>
{% endif %}
{% endfor %}
