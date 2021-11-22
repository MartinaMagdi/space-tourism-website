<template>
  <div class="header">
    <v-row class="header-row">
      <v-col>
        <NuxtLink to="/">
        <img
          class="logo animate__animated animate__slideInLeft"
          src="../static/shared/icons/logo.svg"
        />
        </NuxtLink>
      </v-col>
      <hr class="display-desktop animate__animated animate__wobble" />
      <v-col>
        <div class="desktop animate__animated animate__slideInRight">
          <div class="items">
            <ul>
              <li v-for="item in headerItems" :key="item.id">
                <NuxtLink class="remove-link-style" :to="item.url">
                  <span class="item-number">{{ item.number }}</span>
                  {{ item.name }}</NuxtLink
                >
              </li>
            </ul>
          </div>
        </div>
        <div class="mobile">
          <img
            v-show="!menu"
            class="menu-icon animate__animated animate__slideInRight"
            src="../static/shared/icons/icon-hamburger.svg"
            @click="toggleMenu()"
          />
          <div
            id="side-menu"
            class="side-menu animate__animated animate__slideInRight"
            v-show="menu"
          >
            <img
              class="close-icon"
              src="../static/shared/icons/icon-close.svg"
              @click="toggleMenu()"
            />
            <ul>
              <li
                v-for="item in headerItems"
                :key="item.id"
                @click="toggleMenu()"
                class="animate__animated animate__zoomIn"
              >
                <NuxtLink class="remove-link-style" :to="item.url">
                  <span class="item-number">{{ item.number }}</span>
                  {{ item.name }}</NuxtLink
                >
              </li>
            </ul>
          </div>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      headerItems: [
        {
          id: 1,
          number: "00 ",
          name: "HOME",
          url: "/",
        },
        {
          id: 2,
          number: "01 ",
          name: "DESTINATION",
          url: "/destination",
        },
        {
          id: 3,
          number: "02 ",
          name: "CREW",
          url: "/crew",
        },
        {
          id: 4,
          number: "03 ",
          name: "TECHNOLOGY",
          url: "/technology",
        },
      ],
      menu: false,
    };
  },
  methods: {
    toggleMenu() {
      if (this.menu) {
        document
          .getElementById("side-menu")
          .classList.add("animate__slideOutRight");
        setTimeout(() => {
          this.menu = !this.menu;
        }, 1000);
      } else {
        document
          .getElementById("side-menu")
          .classList.remove("animate__slideOutRight");
        this.menu = !this.menu;
      }
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/variables";

.header {
  font-family: 'Barlow Condensed', sans-serif;
  line-height: 19px;
  letter-spacing: 2.7px;
  .header-row{
    width: 100% !important;
  }
  .remove-link-style {
    color: $third-color;
    text-decoration: unset;
  }
  .item-number {
    font-weight: bold;
  }
  hr {
    position: absolute;
    width: 410px;
    height: 1px;
    left: 167px;
    top: 71px;
    background: #ffffff;
    mix-blend-mode: normal;
    opacity: 0.25;
    z-index: 1;
  }
  .logo {
    margin-top: 3em;
    padding-left: 2em;
    cursor: pointer;
  }

  .desktop {
    background: rgba(255, 255, 255, 0.04);
    backdrop-filter: blur(81.5485px);
    width: 830px;
    height: 83px;
    margin-top: 2em;
    padding: 0.8em 6em;
    .items {
      ul {
        padding: 0;
        display: flex;
        list-style: none;
        li {
          margin: 1em;
          cursor: pointer;
          a {
            padding-bottom: 1.5em;
            &:hover {
              border-bottom: 3px solid #ffffff80;
            }
          }
        }
      }
    }
    a.nuxt-link-exact-active {
      border-bottom: 3px solid $third-color !important;
      padding-bottom: 1.5em;
    }
  }
  .mobile {
    text-align: right;
    .menu-icon {
      margin: 2em;
      cursor: pointer;
    }
    .side-menu {
      height: 100%;
      position: absolute;
      top: 0;
      right: 0;
      z-index: 100000;
      background: rgba(255, 255, 255, 0.04);
      backdrop-filter: blur(81.5485px);
      text-align: left;
      width: 70%;
      padding: 1rem;
      .close-icon {
        position: absolute;
        right: 1.5em;
        top: 1em;
        cursor: pointer;
      }
      ul {
        list-style: none;
        padding: 0;
        margin-top: 5em;
        li {
          cursor: pointer;
          line-height: 19px;
          letter-spacing: 2.7px;
          padding: 1em 0;
        }
      }
    }
  }
}

@media (min-width: $mobiles) and (max-width: $tablets) {
  /* Mobiles */
  .header {
    .desktop,
    .display-desktop {
      display: none;
    }
    .logo {
      padding: 0;
      margin: 1em;
    }
  }
}

@media (min-width: $tablets) and (max-width: $laptops) {
  /* tablet, landscape iPad, lo-res laptops ands desktops */
  .mobile,
  .display-desktop,
  .item-number {
    display: none;
  }
}

@media (min-width: $laptops) {
  /* hi-res laptops and desktops */
  .mobile {
    display: none;
  }
}
</style>