<template>
<div>
  <!-- Auctions section -->
  <div class="text-center">
    <div class="section-banner" ref="auctions">
      <img src="../static/banners/banner-auctions.jpg">
      <div class="banner-border"></div>
    </div>
  </div>
  <div class="section-title">
    <ul>
      <li>
        <input type="checkbox" />
        <div>A</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>U</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>C</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>T</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>I</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>O</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>N</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>S</div>
      </li>
    </ul>
  </div>
  <v-row align="center" justify="center" style="margin-top: 40px">
    <v-col
    cols="12"
    md="6">
      <div class="text-background">
      <div class="paragraph">
      Our <a target="_blank" class="green-link">perpetual auctions</a> provide a way for projects to continuously raise liquidity for their protocols.
      </div>
      <div class="paragraph">
      The Auction contract allows project owners to choose a LP pair and let users donate it to the auction contract.
      </div>
      <div class="paragraph">
      Every 48 hours, the contract will finish the auction and split the auctioned tokens between participants based on their proportional share.
      </div>
      <div class="text-center">
        <a class="animated-button raise">View auctions</a>
        <a class="animated-button raise gray" href="https://docs.toad.network/products/padswap/auctions" target="_blank">Read more</a>
      </div>
      </div>
    </v-col>
    <v-col
    cols="12"
    md="6">
      <div class="text-center">
        <div class="auction-stage">
          <img class="auction-content" src="../static/auctions-animation/toad-auction.png">
          <div class="auction-curtain-left auction-curtain"></div>
          <div class="auction-curtain-right auction-curtain"></div>
          <div class="auction-curtain-top"></div>
          <div class="auction-spotlight"></div>
        </div>
      </div>
    </v-col>
  </v-row>

</div>
</template>
