---
layout: about
title: about
permalink: /
subtitle: (He/Him)

profile:
  align: right
  image: target.jpg
  image_circular: false # crops the image to make it circular
  address: >
    <p>Houston, TX 77005, USA</p>

news: true  # includes a list of news items
selected_papers: false # includes a list of papers marked as "selected={true}"
social: true  # includes social icons at the bottom of the page
---

Welcome! I am a 3rd-year undergrad studying Math & CS at Rice University. My research interests are in AI/ML, optimal transport, and graph representation learning. 

Currently, I am advised by [Dr. Cesar Uribe](https://cauribe.rice.edu/). Previously, I interned at Berkeley AI Research under [Dr. Alison Gopnik](http://www.gopniklab.berkeley.edu/alison) and MD Anderson Cancer Center under [Dr. Jagan Sastry](https://faculty.mdanderson.org/profiles/jagannadha_sastry.html). 

In my free time, I mostly watch movies and TV shows with my little sister. I also try to sprinkle my days with light math reading, a moderate amount of coding, and the occassional basketball games with my friends. 


{% if site.data.repositories.github_users %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.html username=user %}
  {% endfor %}
</div>
{% endif %}

---
