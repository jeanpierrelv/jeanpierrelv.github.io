---
permalink: /
layout: noside
author_profile: false
redirect_from: 
  - /about/
  - /about.html
---

{% include profile-header.html %}

Recent News
======
- **Jan 2026** — Paper accepted at SN Computer Science Journal: "Self-Supervised Learning for Extracting Interpersonal Dynamics in Video Robbery Detection"
- **Jun 2026** — Substitute Professor, Neural Networks and Deep Learning, UNESP
- **Jan 2026** — Substitute Professor, Computer Organization and Architecture, UNESP
- **Dec 2024** — Paper published in Foods Journal on non-destructive morphometric measurements of chicken eggs using computer vision

About me
======
I'm a researcher at the Prisma Research Group at the Department of Statistics, Applied Mathematics and Computing at São Paulo State University, working in the area of ​​computer vision with Deep Learning, researching algorithms to obtain morphometric measurements from 3D tomographic images, and a PhD candidate in Electrical Engineering at UNICAMP. With a Master's in Electrical Engineering (UNICAMP, 2015) and a Bachelor's in Electronic Engineering at San Luis Gonzaga National University of Ica, Perú, 2010. I specialize in Deep Learning, Computer Vision, and System Identification. My research focuses on Time Series Forecasting, and Information Criteria, and I am currently focused on the area of Deep Learning, Computer Vision and Large Language Models to develop innovative AI solutions.

Interests
======
- Computer Vision
- Deep Learning
- Time Series Forecasting
- Information Retrieval
- LLMs
- Control - Identification System
- Robotics - Reinforcemente Learning

Publications
======

You can also find my articles on [my Research Gate profile](https://www.researchgate.net/profile/Jean-Vargas) or [Google Scholar](https://scholar.google.com/citations?user=TC-UZDAAAAAJ).

{% for post in site.publications reversed %}
  <div class="pub-item">
    <div class="pub-title">
      {% if post.paperurl %}
        <a href="{{ post.paperurl }}">{{ post.title }}</a>
      {% else %}
        {{ post.title }}
      {% endif %}
    </div>

    {% if post.citation %}
      <div class="pub-authors">{{ post.citation | strip_html | truncatewords: 25 }}</div>
    {% endif %}

    {% if post.venue %}
      <div class="pub-venue">{{ post.venue }}</div>
    {% endif %}

    {% if post.excerpt and post.excerpt != "" %}
      <button class="pub-abstract-btn" onclick="toggleAbstract(this)">Abstract ▼</button>
      <div class="pub-abstract">{{ post.excerpt }}</div>
    {% endif %}

    {% if post.paperurl or post.content %}
      <div class="pub-links">
        {% if post.paperurl %}
          <a href="{{ post.paperurl }}">📄 Paper</a>
        {% endif %}
      </div>
    {% endif %}
  </div>
{% endfor %}

Portfolio
======

{% for post in site.portfolio reversed %}
  <div class="portfolio-item">
    <h3>{{ post.title }}</h3>
    <div class="portfolio-content">{{ post.excerpt }}</div>
    {% if post.content %}
      {{ post.content | markdownify }}
    {% endif %}
  </div>
{% endfor %}

Teaching
======

{% for post in site.teaching reversed %}
  <div class="teaching-item">
    <h3>{{ post.title }}</h3>
    <p><strong>{{ post.venue }}</strong>, {{ post.date | date: "%Y" }}</p>
    <p>{{ post.type }}</p>
  </div>
{% endfor %}

Timeline
======

<div class="timeline-section">
{% for post in site.teaching reversed %}
  <div class="timeline-item">
    <div class="timeline-date">{{ post.date | date: "%Y" }}</div>
    <div class="timeline-content">
      <h3>{{ post.title }}</h3>
      <p><strong>{{ post.venue }}</strong></p>
      <p>{{ post.type }}</p>
    </div>
  </div>
{% endfor %}
</div>

<script>
function toggleAbstract(button) {
  const abstract = button.nextElementSibling;
  if (abstract.classList.contains('show')) {
    abstract.classList.remove('show');
    button.textContent = 'Abstract ▼';
  } else {
    abstract.classList.add('show');
    button.textContent = 'Abstract ▲';
  }
}
</script>
