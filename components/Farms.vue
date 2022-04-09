<template>
  <div ref="farms">
   <!-- Farms section -->
<!--   <div class="text-center">
    <div class="section-banner" ref="farms">
      <img src="../static/banners/banner-farms.jpg">
      <div class="banner-border"></div>
    </div>
  </div> -->
  <div class="section-title">
    <ul>
      <li>
        <input type="checkbox" />
        <div>F</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>A</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>R</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>M</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>S</div>
      </li>
    </ul>
  </div>
  <v-row align="center" justify="center" style="padding: 50px 0">
    <v-col
    cols="12"
    md="6"
    order="2"
    order-md="1">
    <div class="text-background">
      <div class="paragraph">Farming is our way to incentivize liquidity provision by offering a secure way to make passive income.</div>
      <div class="paragraph">PadSwap offers a wide selection of farms, ranging from safe stablecoin pairs to high-APY partner farms.</div>
      <div class="paragraph">From yield farming to liquidity mining, we've got you covered.</div>
      <div class="text-center">
        <div class="text-center">
          <a class="" href="https://padswap.exchange/farms" target="_blank">
            <div class="animated-button raise">View farms</div>
          </a>
          <a class="" href="https://docs.toad.network/products/padswap/yield-farming" target="_blank">
            <div class="animated-button raise gray">Read more</div>
          </a>
        </div>
      </div>
    </div>
  </v-col>
  <v-col
  cols="12"
  md="6"
  order="1"
  order-md="2">
  <div class="windmill-animation">
    <img class="windmill-farmer-toad" src="../static/farms-animation/farmer-toad.png"></img>
    <img class="windmill-base" src="../static/farms-animation/windmill-base.png">
    <div class="windmill-blades">
      <img src="../static/farms-animation/windmill-blades.png">
    </div>
  </div>
</v-col>
</v-row>

</div>
</template>
