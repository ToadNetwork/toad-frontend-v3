<template>
<div ref="bridge">
<!-- Bridge section -->
<!--   <div class="text-center">
    <div class="section-banner" ref="bridge">
      <img src="../static/banners/banner-bridge.jpg">
      <div class="banner-border"></div>
    </div>
  </div> -->
  <div class="section-title">
    <ul>
      <li>
        <input type="checkbox" />
        <div>B</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>R</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>I</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>D</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>G</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>E</div>
      </li>
    </ul>
  </div>
  <v-row align="center" justify="center">
      <v-col
      cols="12"
      md="6">
        <div class="bridge-animation">
          <div class="mountain"></div>
          <div class="rock"></div>
          <img class="truck" src="../static/bridge-animation/truck.png">
          <img class="wheels" src="../static/bridge-animation/wheels.png">
        </div>
      </v-col>
      <v-col
      cols="12"
      md="6">
      <div class="text-background">
        <div class="paragraph">
          Our <a href="https://v2.padswap.exchange/bridge" target="_blank" class="green-link">cross-chain bridge</a> allows users to easily transfer assets between chains, with a simple and intuitive UI.
        </div>
        <div class="paragraph">
          Provides real-time info about transaction progress, and supports bridging to every chain supported by PadSwap.
        </div>
        <br>
        <div class="text-center">
          <a class="" href="https://v2.padswap.exchange/bridge/" target="_blank">
            <div class="animated-button raise">Use the bridge</div>
          </a>
          <a class="" href="https://docs.toad.network/products/toad-bridge" target="_blank">
            <div class="animated-button raise gray">Read more</div>
          </a>
        </div>
      </div>
      </v-col>
  </v-row>

</div>
</template>
