---
layout: default
title: "Wadi el-Hol"
permalink: /wadi-el-hol/
node: wadi-el-hol

categories: [Origins, Anthologies]
tags:
  - etymology 
  - origin
  - location
  - time
  - narrative
---

{% assign item = site.data.gallery | where: "id", page.node | first %}

{% include hero.html
   image=item.image
   alt=item.alt
   caption=item.caption
   title=item.title
   description=item.description
   links=item.links
%}




<!-- HERO / ENTRY HEADER -->
<section class="my-5 py-4" id="entry-header">
  <div class="container col-xxl-12 px-4">
    <div class="row align-items-center g-5">
      <div class="col-lg-6">
        <figure class="figure">
          <img
            src="{{ '/assets/img/inscriptions.jpg' | relative_url }}"
            class="img-fluid"
            alt="Cracker Jack packaging from the late 19th century"
            loading="lazy"
          />
          <figcaption class="figure-caption hero-caption">
            Inscriptions
          </figcaption>
        </figure>
      </div>
      <div class="col-lg-6">
        <h1 class="display-5 fw-bold lh-1 mb-3">Wadi el-Hol</h1>
        <p class="lead">Carved into the soft limestone cliffs, by Semites some 4000 years ago (during the Middle Kingdom period, 2040-1674 BC), it is here, in Egypt's western desert, that we find the first signs of an alphabetic writing system.</p>
        <nav class="d-flex flex-wrap gap-3 mt-4" aria-label="Related links">
          <a href="#" class="btn btn-outline-secondary btn-lg">Link</a>
          <a href="#" class="btn btn-outline-secondary btn-lg">Link</a>
        </nav>
      </div>
    </div>
  </div>
</section>