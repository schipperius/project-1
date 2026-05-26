---
layout: default
title: Colophon
permalink: /colophon/

image_id: col-da-vinci-bottega
---

{% comment %} 
  1. Index everything
{% endcomment %}

{% assign man_map = site.data.manifest | group_by: "image_id" %}
{% assign loc_map = site.data.location | group_by: "image_id" %}
{% assign attr_map = site.data.attribution | group_by: "image_id" %}
{% assign plate_map = site.plates | group_by: "image_id" %}

{% comment %} 
  2. Perform lookups for the specific image_id defined in front matter
{% endcomment %}

{% assign target_id = page.image_id | append: "" | strip %}

{% assign man = man_map | where: "name", target_id | map: "items" | first | first %}
{% assign loc = loc_map | where: "name", target_id | map: "items" | first | first %}
{% assign attr = attr_map | where: "name", target_id | map: "items" | first | first %}
{% assign plate = plate_map | where: "name", target_id | map: "items" | first | first %}

<article class="container-fluid px-lg-0 my-5">
  <div id="carouselExample" class="carousel slide">

    <div class="carousel-inner">
      <div class="carousel-item active">
        <div class="row g-5">

          <div class="col-lg-8">
            {% if man %}
            <div class="hero-plate-frame p-2 shadow-lg mb-2">
              <a href="{{ man.image_path | relative_url }}" class="lightbox-trigger">
                <img src="{{ man.image_path | relative_url }}" class="img-fluid w-100" alt="{{ man.image_title }}">
              </a>
            </div>

            <div class="d-flex justify-content-between align-items-center px-2 my-2">
              <p class="mb-0 text-muted small">
                {% if loc.place_city %}
                {{ loc.place_city }}{% if loc.place_region %}, {{ loc.place_region }}{% endif %} |
                {% endif %}
                {{ loc.super_period }} | {{ loc.display_year }}
              </p>
            </div>

            <div class="px-2 mt-4">
              <h3 class="display-6">{{ man.image_title }}</h3>
              {% comment %} Fallback: Plate caption > man caption > man Title {% endcomment %}
              <p class="lead">
                {{ plate.image_caption | default: man.image_caption | default: man.image_title }}
              </p>
            </div>

            {% else %}
            <div class="alert alert-warning">
              Data for ID <strong>{{ target_id }}</strong> not found in master man.
            </div>
            {% endif %}
          </div>

          <div class="col-lg-4">
            <div class="mb-4">
              <p class="lead text-body-secondary">The Book of Jack was initially conceived as a coffee table book.</p>
              <p>The history of writing and publishing is marked by diverse spaces, from sacred "Houses of Life" to
                industrial
                print shops, each reflecting the technology and culture of its era...</p>
            </div>

            <div class="mt-4">
              {% comment %} Using status from the attribution or man file {% endcomment %}
              {% if attr.status == "verified" or man.status == "verified" %}
              <span class="badge bg-success">Museum Verified</span>
              {% else %}
              <span class="badge border text-secondary">Research in Progress</span>
              {% endif %}
            </div>
          </div>

          <hr class="my-5">
          <div class="mt-4">
            {{ plate.content | markdownify }}
          </div>
          
        </div>
      </div>

      <div class="carousel-item">
        <img src="..." class="d-block w-100" alt="...">
      </div>
      <div class="carousel-item">
        <img src="..." class="d-block w-100" alt="...">
      </div>
    </div>

    <button class="carousel-control-prev" type="button" data-bs-target="#carouselExample" data-bs-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Previous</span>
    </button>
    <button class="carousel-control-next" type="button" data-bs-target="#carouselExample" data-bs-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Next</span>
    </button>

  </div>
</article>

