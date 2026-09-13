---
permalink: /
layout: home
title: "Koki Seno"
seo_title: "Koki Seno | Robot Learning | Keio University"
description: "Koki Seno is a first-year Master's student at Keio University researching robot learning, learning from human videos, and generative models."
excerpt: "Koki Seno is a first-year Master's student at Keio University researching robot learning, learning from human videos, and generative models."
author_profile: false
sidebar: false
redirect_from:
  - /about/
  - /about.html
---

<p>
I am a first-year Master's student in Human and Social Systems Information Science at the Graduate School of Science and Technology, Keio University, advised by Prof. <a href="https://komeisugiura.jp/index_en.html">Komei Sugiura</a>. My research interests include robot learning, learning from human videos, and generative models such as flow matching. I received my Bachelor's degree from the Department of Information and Computer Science, Faculty of Science and Technology, Keio University.
</p>

<h2 id="research-interests">Research Interests</h2>
<ul>
  <li>Robot Learning</li>
  <li>Learning from Human Videos</li>
  <li>Generative Models (e.g., Flow Matching)</li>
</ul>

<h2 id="news">News</h2>
<div class="news">
<ul>
  <li><span class="date">2026/09</span> Two papers were accepted to CoRL 2026.</li>
  <li><span class="date">2026/09</span> Received two awards at RSJ 2026.</li>
  <li><span class="date">2026/06</span> Two papers were accepted to IROS 2026.</li>
  <li><span class="date">2026/06</span> Our paper "Flow as Flow" is out!</li>
  <li><span class="date">2026/03</span> A paper was accepted to IEEE RA-L.</li>
</ul>
</div>

<h2 id="publications">Publications</h2>

{% include base_path %}
{% assign all_pubs = site.publications | sort: "date" | reverse %}
{% for post in all_pubs %}
{% if post.category == "manuscripts" %}
{% include publication-entry.html post=post %}
{% endif %}
{% endfor %}

{% assign preprints = all_pubs | where: "category", "preprints" %}
{% if preprints.size > 0 %}
<h2 id="preprints">Preprints</h2>

{% for post in preprints %}
{% include publication-entry.html post=post %}
{% endfor %}
{% endif %}

<h2 id="domestic-conferences">Domestic Conferences</h2>

{% for post in all_pubs %}
{% if post.category == "domestic" %}
{% include publication-entry.html post=post %}
{% endif %}
{% endfor %}

<h2 id="awards">Awards</h2>

{% assign awards = site.data.awards | sort: "date" | reverse %}
{% for award in awards %}
<div class="pub">
<div class="pub-body">
<div class="pub-title">{{ award.title | escape }}</div>
<div class="pub-authors">{{ award.recipients }}</div>
<div class="pub-venue"><em>{{ award.venue | escape }}</em>, <time datetime="{{ award.date | date: '%Y-%m-%d' }}">{{ award.date | date: '%-d %B %Y' }}</time></div>
</div>
</div>
{% endfor %}
