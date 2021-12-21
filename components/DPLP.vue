<template>
<div>
<!-- DPLP section -->
  <div class="text-center">
    <div class="section-banner" ref="dplp">
      <img src="../static/banners/banner-dplp.jpg">
      <div class="banner-border"></div>
    </div>
  </div>
  <div class="section-title">
    <ul>
      <li>
        <input type="checkbox" />
        <div>D</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>P</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>L</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>P</div>
      </li>
    </ul>
  </div>
  <v-row align="center" justify="center" style="padding: 50px 0">
    <v-col
    cols="12"
    md="6"
    >
    <div class="text-center">
      <div class="video-container">
        <iframe src="https://www.youtube.com/embed/IAMNJRaDaLk?t=14" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
      </div>
    </div>
    </v-col>
    <v-col
    cols="12"
    md="6"
    >
    <div class="text-background">
      <div class="paragraph">
        DPLP, or perpetual LP farming, is a new concept we invented at TOAD Network, the goal of which is to ensure that a project will always have enough liquidity.
      </div>
      <div class="paragraph">
        Unlike using a simple liquidity lock, DPLP attracts users to your project and encourages them to add their own liquidity, while still making it impossible to drain the liquidity pool.
      </div>
      <div class="text-center">
        <a class="animated-button raise" href="https://dapps.padswap.exchange/lpfarms" target="_blank">DPLP farms</a>
        <a class="animated-button raise gray" href="https://docs.toad.network/products/dplp" target="_blank">Read more</a>
      </div>
    </div>
    </v-col>
  </v-row>

</div>
</template>
