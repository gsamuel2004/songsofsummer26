---
layout: default
title: Home
---

<section class="hero">
  <div class="hero__content">
    <p class="eyebrow">The seasonal soundtrack</p>
    <h1>Top 10 Songs<br><span>of the Summer</span></h1>
    <p class="hero__lede">A space for thoughtful reviews, memorable hooks, and the songs that made this summer unforgettable.</p>
    <a class="button" href="#rankings">Explore the rankings <span aria-hidden="true">↓</span></a>
  </div>
  <div class="hero__art" aria-hidden="true">
    <div class="sun"></div>
    <div class="record record--one"></div>
    <div class="record record--two"></div>
    <div class="spark spark--one">✦</div>
    <div class="spark spark--two">✦</div>
  </div>
</section>

<section class="intro section-wrap">
  <p class="eyebrow">About the project</p>
  <h2>A listening guide for the season.</h2>
  <p class="intro__text">Use this homepage to introduce your project, explain your ranking criteria, and share what “song of the summer” means to you. Replace this placeholder text with your own introduction.</p>
</section>

<section id="rankings" class="rankings section-wrap">
  <div class="section-heading">
    <div>
      <p class="eyebrow">The countdown</p>
      <h2>Meet the top 10</h2>
    </div>
    <p class="section-note">Your reviews, one track at a time.</p>
  </div>
  <div class="song-grid">
    {% assign ranked_songs = site.songs | sort: "rank" %}
    {% for song in ranked_songs %}
      <a class="song-card" href="{{ song.url | relative_url }}">
        <div class="song-card__number">{{ song.rank | prepend: "0" | slice: -2, 2 }}</div>
        <div class="song-card__body">
          <p class="song-card__artist">{{ song.artist }}</p>
          <h3>{{ song.title }}</h3>
          <span class="song-card__link">Read review <span aria-hidden="true">↗</span></span>
        </div>
      </a>
    {% endfor %}
  </div>
</section>
