<template>
<div ref="padswap">
<!--   <div class="text-center">
    <div class="section-banner" ref="padswap">
      <img src="../static/banners/banner-padswap.jpg">
      <div class="banner-border"></div>
    </div>
  </div> -->
    <div class="section-title">
    <ul>
      <li>
        <input type="checkbox" />
        <div>P</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>A</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>D</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>S</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>W</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>A</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>P</div>
      </li>
    </ul>
  </div>

  <v-row style="margin-top: 50px" align="center" justify="center">
    <v-col
      class="main-column"
      cols="12"
      xs="12"
      sm="12"
      md="6"
      lg="6"
      xl="6"
      style="text-align: center"
      >
      <div class="pad-playing-card">
        <div class='pad-playing-card-wrapper'>
        <img class='pad-playing-card-back' src='../static/padswap-animation/card-back.png'>
        <img class='pad-playing-card-front' src='../static/padswap-animation/card-front.png'>
        </div>
      </div>
    </v-col>
    <v-col
      class="main-column"
      cols="12"
      xs="12"
      sm="12"
      md="6"
      lg="6"
      xl="6"
      align-self="center"
      >
      <div class="text-background">
        <div class="paragraph">PadSwap is our own multi-chain AMM.<br>Built with a Vault system, PADSwap's fees are used to back PAD, its native token.</div>
        <br>
        <div class="paragraph">PadSwap is heavily focused on fairness and security, with a rug-proof DPLP protocol and some of the best incentives for providing liquidity on the platform.</div>
        <div class="text-center">
          <a class="" href="https://dapps.padswap.exchange/swap" target="_blank">
            <div class="animated-button raise">Use PadSwap</div>
          </a>
          <a class="" href="https://docs.toad.network/products/padswap" target="_blank">
            <div class="animated-button raise gray">Read more</div>
          </a>
        </div>
      </div>
    </v-col>
  </v-row>

</div>
</template>
