<template>
  <v-app>
    <v-app-bar
      style="background:transparent; box-shadow: none"
      :clipped-left="clipped"
      absolute
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" class="hidden-md-and-up"></v-app-bar-nav-icon>
      <a href="/">
      <img
      class="mr-3"
      src="https://d33wubrfki0l68.cloudfront.net/4e5f36d85fde5cbd2921b558e4a36ba2d8a3278f/93d03/assets/images/logo.png"
      height="40"/>
      </a>
      <v-spacer></v-spacer>
      <div class="hidden-sm-and-down dappsanav">
      <v-menu
      v-for="(item, index) in navbar"
      :key="index"
      rounded="lg"
      offset-y
      open-on-hover
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            v-ripple="false"
            style="background:transparent !important; box-shadow:none"
            v-bind="attrs"
            v-on="on"
          >
            <img src="../static/menu-icons/Bridge Icon.svg">
            <!-- <v-icon style="margin-right: 5px" small>{{ item.icon }}</v-icon> -->
            {{ item.title }}
          </v-btn>
        </template>

        <v-list>
          <v-list-item
            v-for="(subitem, subindex) in item.subItems"
            :key="subindex"
            :to="subitem.to"
            :href="subitem.href"
            :target="subitem.target"
          >
            <v-icon style="margin-right: 10px">{{ subitem.icon }}</v-icon>
            <v-list-item-title>
              {{ subitem.title }}
              <div class="description">{{ subitem.description }}</div>
            </v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
      </div>
      <v-icon @click="switchTheme()">{{ "mdi-theme-light-dark" }}</v-icon>
      <v-btn
      id="connect-btn"
      @click="connect()"
      style="margin-right:10px; margin-left: 10px; border-radius:12px; background: rgba(0, 0, 0, 0) linear-gradient(128.17deg, rgb(0, 255, 77) -14.78%, rgb(117, 113, 255) 110.05%) repeat scroll 0% 0%;"
      >
      {{connected}}
      </v-btn>
    </v-app-bar>
    <v-navigation-drawer
      class="hidden-md-and-up"
      v-model="drawer"
      fixed
      floating
    >
      <v-list-item-action @click.stop="drawer = !drawer" >
            <v-icon>{{ "mdi-close" }}</v-icon>
      </v-list-item-action>
      <v-list>
        <v-list-group
        v-for="(item, index) in navbar"
        :key="index"
        v-model="item.active"
        :prepend-icon="item.action"
        no-action
        >
        <template v-slot:activator>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" active></v-list-item-title>
          </v-list-item-content>
        </template>

        <v-list-item
          v-for="(subitem, subindex) in item.subItems"
          :key="subindex"
          :to="subitem.to"
          :href="subitem.href"
          :target="subitem.target"
        >
          <v-list-item-content>
            <v-list-item-title v-text="subitem.title"></v-list-item-title>
            <div class="description">{{ subitem.description }}</div>
          </v-list-item-content>
        </v-list-item>
      </v-list-group>
    </v-list>
    </v-navigation-drawer>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import WalletConnectProvider from '@walletconnect/web3-provider'
import Web3 from 'web3'
import Web3Modal from 'web3modal'
const web3Modal = new Web3Modal({
  network: 'binance', // replace mainnet to binance
  cacheProvider: false,
  providerOptions: {
    walletconnect: {
      package: WalletConnectProvider,
      options: {
        rpc: {
          56: 'https://bsc-dataseed1.defibit.io/'
        },
        bridge: 'https://pancakeswap.bridge.walletconnect.org/',
        network: 'binance'
      }
    }
  }
})
web3Modal.clearCachedProvider()
export default {
  mounted () {
    this.dataseed = new Web3('https://bsc-dataseed1.binance.org:443')
  },
  data () {
    return {
      web3: null,
      connected: 'Connect',
      clipped: false,
      drawer: false,
      fixed: false,
      navbar: [
        {
          title: 'Products',
          icon: 'mdi-swap-horizontal',
          active: true,
          subItems: [
            {
              title: 'Swap',
              icon: 'mdi-swap-horizontal',
              active: true,
              description: 'Buy or sell any token instantly on PadSwap',
              href: 'https://padswap.toad.network/#/swap',
              target: '_self'
            },
            {
              title: 'LaunchPad',
              icon: 'mdi-rocket-launch',
              description: 'Partake in exclusive presales',
              href: 'https://padswap.toad.network/launchpad',
              target: '_self'
            },
            {
              title: 'Bridge',
              icon: 'mdi-bridge',
              description: 'Bridge tokens between chains',
              href: 'https://padswap.toad.network/bridge',
              target: '_self'
            },
            {
              title: 'Vault',
              icon: 'mdi-safe-square-outline',
              description: 'PAD\'s backing reserves',
              href: 'https://padswap.toad.network/vault',
              target: '_self'
            },
            {
              title: 'Farms',
              icon: 'mdi-sprout',
              description: 'Earn passive income by staking liquidity',
              href: 'https://padswap.toad.network/farms',
              target: '_self'
            },
            {
              title: 'Farms (old)',
              icon: 'mdi-spa-outline',
              description: 'Our old farms using PCSv1 liquidity',
              to: '/toad'
            },
            {
              title: 'Stats',
              icon: 'mdi-chart-bar',
              description: 'Analyze token prices and their volume',
              href: 'https://info.padswap.toad.network/home',
              target: '_self'
            }
          ]
        },
        {
          title: 'Content',
          icon: 'mdi-play-circle-outline',
          subItems: [
            {
              title: 'TOAD Academy',
              icon: 'mdi-school-outline',
              description: 'Learn about crypto in a fun way',
              href: 'https://toad.academy/',
              target: '_blank'
            },
            {
              title: 'Games',
              icon: 'mdi-gamepad-variant-outline',
              description: 'Play our TOAD-themed games',
              href: 'https://toad.academy/games',
              target: '_blank'
            },
            {
              title: 'YouTube',
              icon: 'mdi-youtube',
              description: 'Watch our series of educational animated videos',
              href: 'https://www.youtube.com/channel/UCI_vUc-HrJWtKXj-Re-hTSw',
              target: '_blank'
            },
            {
              title: 'Pyramid Store',
              icon: 'mdi-tshirt-crew-outline',
              description: 'Official TOAD merch',
              href: 'https://piramyd.me/toad-network-x-piramyd/',
              target: '_blank'
            }
          ]
        },
        {
          title: 'Socials',
          icon: 'mdi-account-multiple',
          subItems: [
            {
              title: 'Telegram',
              icon: 'mdi-send',
              description: 'Come chat with us on Telegram',
              href: 'https://t.me/toadnetwork',
              target: '_blank'
            },
            {
              title: 'Reddit',
              icon: 'mdi-reddit',
              description: 'Partake in discussions about Toad.Network on our subreddit',
              href: 'https://reddit.com/r/toadnetwork',
              target: '_blank'
            },
            {
              title: 'Twitter',
              icon: 'mdi-twitter',
              description: 'Stay up to date with our latest news',
              href: 'https://twitter.com/toadnetwork',
              target: '_blank'
            }
          ]
        },
        {
          title: 'About',
          icon: 'mdi-help-circle-outline',
          subItems: [
            {
              title: 'TOAD Docs',
              icon: 'mdi-clipboard-text-search-outline',
              description: 'Learn all about TOAD on our Wiki',
              href: 'https://docs.toad.network/',
              target: '_blank'
            },
            {
              title: 'TOAD Audit Report',
              icon: 'mdi-text-box-check',
              description: 'TOAD audit report by SpadeAudits',
              href: '/toad_audit_report.pdf',
              target: '_blank'
            },
            {
              title: 'PAD Audit Report',
              icon: 'mdi-text-box-check',
              description: 'PadSwap contracts audit report by SpadeAudits',
              href: '/pad_audit_report.pdf',
              target: '_blank'
            },
            {
              title: 'White Paper',
              icon: 'mdi-file-outline',
              description: 'PadSwap white paper',
              href: 'https://www.dropbox.com/s/bng5e1bq2u03bk6/PAD%20WHITEPAPER.PDF',
              target: '_blank'
            }
          ]
        },
        {
          title: 'Buy TOAD',
          subItems: [
            {
              title: 'PadSwap',
              description: 'Trade TOAD on our own exchange',
              href: 'https://padswap.toad.network/#/swap?inputCurrency=0x463e737d8f740395abf44f7aac2d9531d8d539e9',
              target: '_blank'
            },
            {
              title: 'PancakeSwap',
              description: 'Trade TOAD on PancakeSwap v1',
              href: 'https://pancake.toad.network/#/swap?inputCurrency=0x463e737d8f740395abf44f7aac2d9531d8d539e9',
              target: '_blank'
            },
            {
              title: 'XT',
              description: 'Trade on XT.com',
              href: 'https://www.xt.com/tradePro/toad_usdt',
              target: '_blank'
            },
            {
              title: 'Chart',
              description: 'Price chart, provided by DexGuru',
              href: 'https://dex.guru/token/0x463e737d8f740395abf44f7aac2d9531d8d539e9-bsc',
              target: '_blank'
            }
          ]
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Toad Network'
    }
  },

  methods: {
    async connect () {
      const provider = await web3Modal.connect()
      const web3 = new Web3(provider)
      const accounts = await web3.eth.getAccounts()
      if (!provider.selectedAddress) { provider.selectedAddress = accounts[0] }
      this.connected = provider.selectedAddress.substring(0, 3) + '...' + provider.selectedAddress.substring(provider.selectedAddress.length - 3, provider.selectedAddress.length)
      this.myAddress = provider.selectedAddress
      this.web3 = web3
    },
    switchTheme () {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
      localStorage.setItem('theme', this.$vuetify.theme.dark ? 'dark' : 'light')
    }
  }
}
</script>
<style scoped>
.v-sheet.theme--light > .v-toolbar__content > .dappsanav > .v-btn{
  color: #4c4c4c !important;
}
.v-sheet.theme--light > .v-toolbar__content > #connect-btn{
  color: white !important;
}
.theme--dark.v-application {
  background: rgb(0 0 0 / 92%) !important;
  color: #FFFFFF;
}
.theme--dark.v-navigation-drawer{
  background-color:rgb(33, 36, 41);
}
.v-navigation-drawer {
  z-index: 10;
  width: 96vw !important;
  margin-left:2vw;
  height: 97vh !important;
  top: 1.5vh !important;
  border-radius: 10px !important;
}
.v-list-item__action {
  margin-bottom: 0px;
  margin-left: calc(93vw - 25px);
  margin-top: 30px;
  cursor: pointer;
}
.v-application--is-ltr .v-list-group--no-action > .v-list-group__items > .v-list-item {
    padding-left: 32px;
}
.v-list-item__action {
  margin-bottom: 0px;
  margin-left: calc(93vw - 25px);
  margin-top: 30px;
  cursor: pointer;
}
.v-application--is-ltr .v-list-group--no-action > .v-list-group__items > .v-list-item {
    padding-left: 32px;
}
.theme--dark.v-application {
    background: rgb(0 0 0 / 92%) !important;
    color: #FFFFFF;
}
.description {
  margin-top: 2px;
  font-size: 0.825rem;
  width: -moz-fit-content;
  color: rgb(136, 141, 155);
}
header { position: absolute; }
</style>

<style>
  @import '../styles/style.css';
</style>
