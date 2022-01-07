<template>
  <v-app>
    <v-app-bar
      id="nav-bar"
      style="background:transparent; box-shadow: none"
      :clipped-left="clipped"
      fixed
      app
    >
      <a href="/">
      <img
      class="mr-3"
      src="https://d33wubrfki0l68.cloudfront.net/4e5f36d85fde5cbd2921b558e4a36ba2d8a3278f/93d03/assets/images/logo.png"
      height="40"/>
      </a>
      <v-spacer></v-spacer>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" class="hidden-md-and-up"></v-app-bar-nav-icon>
      <div class="hidden-sm-and-down">
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
            dark
            v-bind="attrs"
            v-on="on"
          >
            <v-icon style="margin-right: 5px" small>{{ item.icon }}</v-icon>
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
            <img :src="subitem.icon" style="width: 20px; margin-right: 13px;">
            <!-- <v-icon style="margin-right: 10px">{{ subitem.icon }}</v-icon> -->
            <v-list-item-title>
              {{ subitem.title }}
              <div class="description">{{ subitem.description }}</div>
            </v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
      <v-btn
      href="https://dapps.padswap.exchange/"
      target="_blank"
      style="border-radius:12px; background: rgba(0, 0, 0, 0) linear-gradient(128.17deg, rgb(0, 255, 77) -14.78%, rgb(117, 113, 255) 110.05%) repeat scroll 0% 0%;"
      >
      Launch App
      </v-btn>
      </div>
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
    <v-footer
      :absolute="!fixed"
      app
    >
      <span>Toad.Network &copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
const debounce = (fn) => {
  let frame
  return (...params) => {
    if (frame) {
      cancelAnimationFrame(frame)
    }
    frame = requestAnimationFrame(() => {
      fn(...params)
    })
  }
}

const storeScroll = () => {
  document.documentElement.dataset.scroll = window.scrollY
}
document.addEventListener('scroll', debounce(storeScroll), { passive: true })
storeScroll()

export default {
  data () {
    return {
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
              icon: 'icons/Swap Icon.svg',
              active: true,
              description: 'Buy or sell any token instantly on PadSwap',
              href: 'https://padswap.exchange/#/swap',
              target: '_self'
            },
            {
              title: 'LaunchPad',
              icon: 'icons/LaunchPAD Icon.svg',
              description: 'Partake in exclusive presales',
              href: 'https://dapps.padswap.exchange/launchpad',
              target: '_self'
            },
            {
              title: 'Bridge',
              icon: 'icons/Bridge Icon.svg',
              description: 'Bridge tokens between chains',
              href: 'https://dapps.padswap.exchange/bridge',
              target: '_self'
            },
            {
              title: 'Vault',
              icon: 'icons/Vault Icon.svg',
              description: 'PAD\'s backing reserves',
              href: 'https://dapps.padswap.exchange/vault',
              target: '_self'
            },
            {
              title: 'Farms',
              icon: 'icons/Farms Icon.svg',
              description: 'Earn passive income by staking liquidity',
              href: 'https://dapps.padswap.exchange/',
              target: '_self'
            },
            {
              title: 'Farms (old)',
              icon: 'icons/Pad Icon.svg',
              description: 'Our old farms using PCSv1 liquidity',
              to: '/toad'
            },
            {
              title: 'Stats',
              icon: 'icons/Stats Icon.svg',
              description: 'Analyze token prices and their volume',
              href: 'https://info.padswap.exchange/home',
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
              icon: 'icons/TOADAcademy Icon.svg',
              description: 'Learn about crypto in a fun way',
              href: 'https://toad.academy/',
              target: '_blank'
            },
            {
              title: 'Games',
              icon: 'icons/Games Icon.svg',
              description: 'Play our TOAD-themed games',
              href: 'https://toad.academy/games',
              target: '_blank'
            },
            {
              title: 'YouTube',
              icon: 'icons/YouTube Icon.svg',
              description: 'Watch our series of educational animated videos',
              href: 'https://www.youtube.com/channel/UCI_vUc-HrJWtKXj-Re-hTSw',
              target: '_blank'
            },
            {
              title: 'Piramyd Store',
              icon: 'icons/Piramyd Store Icon.svg',
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
              icon: 'icons/Telegram Icon.svg',
              description: 'Come chat with us on Telegram',
              href: 'https://t.me/toadnetwork',
              target: '_blank'
            },
            {
              title: 'Reddit',
              icon: 'icons/Reddit Icon.svg',
              description: 'Partake in discussions about Toad.Network on our subreddit',
              href: 'https://reddit.com/r/toadnetwork',
              target: '_blank'
            },
            {
              title: 'Twitter',
              icon: 'icons/Twitter Icon.svg',
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
              icon: 'icons/Docs Icon.svg',
              description: 'Learn all about TOAD on our Wiki',
              href: 'https://docs.toad.network/',
              target: '_blank'
            },
            {
              title: 'TOAD Audit Report',
              icon: 'icons/Audit Icon.svg',
              description: 'TOAD audit report by SpadeAudits',
              href: '/toad_audit_report.pdf',
              target: '_blank'
            },
            {
              title: 'PAD Audit Report',
              icon: 'icons/Audit Icon.svg',
              description: 'PadSwap contracts audit report by SpadeAudits',
              href: '/pad_audit_report.pdf',
              target: '_blank'
            },
            {
              title: 'White Paper',
              icon: 'icons/White Paper Icon.svg',
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
              icon: 'icons/Pad Icon.svg',
              href: 'https://padswap.exchange/#/swap?inputCurrency=0x463e737d8f740395abf44f7aac2d9531d8d539e9',
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
              icon: 'icons/Stats Icon.svg',
              href: 'https://dex.guru/token/0x463e737d8f740395abf44f7aac2d9531d8d539e9-bsc',
              target: '_blank'
            }
          ]
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Toad.Network'
    }
  },
  watch: {
    group () {
      this.drawer = false
    }
  },
  methods: {
    switchTheme () {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
      localStorage.setItem('theme', this.$vuetify.theme.dark ? 'dark' : 'light')
    }
  }
}
</script>

<style scoped>

html:not([data-scroll="0"]) #nav-bar {
  background-color: #000000c7 !important;
}

.v-btn {text-transform: capitalize; font-size:1rem; font-weight:400; letter-spacing:1px}
.v-btn:hover:before { background-color: transparent }
.v-btn:before { background-color: transparent }
.v-list-item {cursor: pointer;}
.v-list-item--link::before {background: transparent}
.v-list-item--link:hover {transform: translate3d(2px, 2px, 10px);}
.v-btn:hover {transform: translate3d(2px, 2px, 10px);}
.v-menu__content--fixed {margin-left:12px}
.description {
  margin-top: 2px;
  font-size: 0.825rem;
  width: -moz-fit-content;
  color: rgb(136, 141, 155);
}
.v-navigation-drawer {
  z-index: 10;
  width: 96vw !important;
  margin-left:2vw;
  background-color:rgb(33, 36, 41);
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
.theme--dark.v-application {
    background: rgb(0 0 0 / 92%) !important;
    color: #FFFFFF;
}
</style>

<style>
  @import '../styles/style.css';
</style>
