<template>
<div>
  <!-- Vault section -->
  <div class="text-center">
    <div class="section-banner" ref="vault">
      <img src="../static/banners/banner-vault.jpg">
      <div class="banner-border"></div>
    </div>
  </div>
  <div class="section-title">
    <ul>
      <li>
        <input type="checkbox" />
        <div>V</div>
      </li>
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
        <div>L</div>
      </li>
      <li>
        <input type="checkbox" />
        <div>T</div>
      </li>
    </ul>
  </div>
  <br><br>
  <v-row align="center" justify="center" style="margin-top: 40px">
    <v-col
    cols="12"
    md="6">
      <div class="text-center">
      <div class="curtain">
      <div class="curtain__wrapper">
      <input type="checkbox" checked>

      <div class="curtain__panel curtain__panel--left">
        <!-- <h1 class="vault-letterpress" style="text-align: right">CLICK TO&nbsp;</h1> -->
      </div>

    <div class="curtain__content">
      <ul class="circles">
        <li><img src="../static/icon-pad.png"></li>
        <li><img src="../static/icon-pad.png"></li>
        <li><img src="../static/token-icons/bnb.png"></li>
        <li><img src="../static/token-icons/bnb.png"></li>
        <li><img src="../static/token-icons/btc.png"></li>
        <li><img src="../static/token-icons/btc.png"></li>
        <li><img src="../static/token-icons/doge.png"></li>
        <li><img src="../static/token-icons/doge.png"></li>
        <li><img src="../static/token-icons/dot.png"></li>
        <li><img src="../static/token-icons/dot.png"></li>
        <li><img src="../static/token-icons/eth.png"></li>
        <li><img src="../static/token-icons/eth.png"></li>
        <li><img src="../static/token-icons/toad.png"></li>
        <li><img src="../static/token-icons/toad.png"></li>
        <li><img src="../static/token-icons/usdc.png"></li>
        <li><img src="../static/token-icons/usdc.png"></li>
      </ul>
    </div>

    <div class="curtain__panel curtain__panel--right">
       <!-- <h1 class="vault-letterpress" style="text-align: leeft">&nbsp;ACCESS</h1> -->
    </div>

    </div>
    </div>
      </div>
    </v-col>
    <v-col
    cols="12"
    md="6">
      <div class="text-background">
        <div class="paragraph">
        Whenever a transaction takes place on PADSwap, a portion of the fees go to <a href="https://dapps.padswap.exchange/vault/" target="_blank" class="green-link">the Vault</a>.
        </div>
        <div class="paragraph">
        The tokens accumulated in The Vault act as a backing for PAD, giving it real value in underlying tokens (such as BNB, BTC, ETH, and any other tokens used on PadSwap).
        </div>
        <div class="paragraph">
        By giving users the ability to burn PAD at any time and receive its backing, the Vault creates a permanent price floor and guarantees that PAD will always have value.
        </div>
        <div class="text-center">
        <a class="animated-button raise" href="https://dapps.padswap.exchange/vault/" target="_blank">Access vault</a>
        <a class="animated-button raise gray" href="https://docs.toad.network/products/padswap/the-vault" target="_blank">Read more</a>
        </div>
      </div>
    </v-col>
  </v-row>

</div>
</template>
