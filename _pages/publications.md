---
layout: page
permalink: /publications/
title: publications
description:
years: [2019, 2015]
nav: true
order: 2
---

These paper can also be found on my [Google Scholar](https://scholar.google.com/citations?user=OIgTlqEAAAAJ) and [ResearchGate](https://www.researchgate.net/profile/Ka_Ming_Fung) pages.

<div class="publications">

{% for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]*%}
{% endfor %}

</div>
