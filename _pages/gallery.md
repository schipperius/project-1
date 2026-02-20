---
layout: default
title: Gallery
permalink: /gallery/
---

<section class="py-5">
  <div class="container">
    <!-- Section Header -->
    <div class="d-flex justify-content-between align-items-center mb-4">
      <h2 class="mb-0">Gallery Title</h2>
      <p class="lead">sub title</p>
      <!-- Arrows only visible on lg+ -->
    </div>
    <!-- Card Grid -->
    <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
      <!-- Card 1 -->
      <div class="col">
        <div class="card h-100">
          <a href="{{ '/cracker-jack/' | relative_url }}" class="text-decoration-none text-dark">
            <img src="{{'/assets/img/cracker-jack.jpg' | relative_url }}" class="card-img-top" alt="">
          </a>  
          <div class="card-body">
            <h5 class="card-title">Card Title</h5>
            <p class="card-text">Description</p>
          </div>
        </div>
      </div>
      <!-- Card 2 -->
      <div class="col">
        <div class="card h-100">
          <a href="{{ '/wadi-el-hol/' | relative_url }}" class="text-decoration-none text-dark">
            <img src="{{'/assets/img/wadi-el-hol.png' | relative_url }}" class="card-img-top" alt="">
          </a>  
          <div class="card-body">
            <h5 class="card-title">Card Title</h5>
            <p class="card-text">Description</p>
          </div>
        </div>
      </div>
      <!-- Card 3 -->
      <div class="col">
        <div class="card h-100">
          <a href="{{ '/wadi-el-hol/' | relative_url }}" class="text-decoration-none text-dark">
            <img src="{{'/assets/img/wadi-3.png' | relative_url }}" class="card-img-top" alt="">
          </a>  
          <div class="card-body">
            <h5 class="card-title">Card Title</h5>
            <p class="card-text">Description</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
