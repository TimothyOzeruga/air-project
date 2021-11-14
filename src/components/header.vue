<template>
  <header>
    <nav class="header__top" :class="{ header__top_non: scrollDownn }">
      <div class="header__container">
        <ul class="nav__list">
          <li class="nav__item">
            <a href="#" class="nav__link">air.io</a>
          </li>
          <li class="nav__item">
            <a href="#" class="nav__link">creators ecosystem</a>
          </li>
          <li class="nav__item">
            <a href="#" class="nav__link">brands</a>
          </li>
          <li class="nav__item">
            <a href="#" class="nav__link">career</a>
          </li>
          <li class="nav__item">
            <a href="#" class="nav__link">blog</a>
          </li>
          <li class="nav__item">
            <a href="#" class="nav__link">f.a.q.</a>
          </li>
        </ul>
        <button
          @click="mobMenu"
          :class="{ is_active: isOpenMobMenu }"
          class="hamburger hamburger--elastic"
          type="button"
        >
          <span class="hamburger-box">
            <span class="hamburger-inner"></span>
          </span>
        </button>
        <div class="nav__bar">
          <select>
            <option value="/en/" selected>RU</option>
            <option value="/es/">EN</option>
            <option value="/es/">ES</option>
          </select>
          <div class="menu__btn">
            <a href="#" class="menu__btn_link"
              ><img src="~@/assets/images/btn.png" alt="btn"
            /></a>
          </div>
        </div>
      </div>
    </nav>
    <div id="mobile_menu_block">
      <nav class="mobile_menu">
        <ul>
          <li @click="mobMenu" class="menu_item">
            <a href="#" class="item_link">air.io</a>
          </li>
          <li @click="mobMenu" class="menu_item">
            <a href="#" class="item_link">creators ecosystem</a>
          </li>
          <li @click="mobMenu" class="menu_item">
            <a href="#" class="item_link">brands</a>
          </li>
          <li @click="mobMenu" class="menu_item">
            <a href="#" class="item_link">career</a>
          </li>
          <li @click="mobMenu" class="menu_item">
            <a href="#" class="item_link">blog</a>
          </li>
          <li @click="mobMenu" class="menu_item">
            <a href="#" class="item_link">f.a.q.</a>
          </li>
        </ul>
      </nav>
    </div>
    <nav
      class="header__bottom"
      :class="{ header__bottom_down: scrollDown, header__bottom_up: scrollUp }"
    >
      <div class="header__container header__line">
        <div class="logo">
          <a href="#" class="logo__name" :class="{ link__scroll: linkScroll }"
            >AIR Collab</a
          >
        </div>
        <ul class="menu__list">
          <li class="menu__item item">
            <a
              href="#collab"
              class="item__link"
              :class="{
                link__scroll: linkScroll,
                small_window_link: smallWindowLink,
              }"
              >AIR Collab</a
            >
          </li>
          <li class="menu__item item">
            <a
              href="#about"
              class="item__link"
              :class="{
                link__scroll: linkScroll,
                small_window_link: smallWindowLink,
              }"
              >About AIR Collab</a
            >
          </li>
          <li class="menu__item item">
            <a
              href="#section"
              class="item__link"
              :class="{
                link__scroll: linkScroll,
                small_window_link: smallWindowLink,
              }"
              >Service</a
            >
          </li>
          <li class="menu__item item">
            <a
              href="#"
              class="item__link"
              :class="{
                link__scroll: linkScroll,
                small_window_link: smallWindowLink,
              }"
              >Success Stories</a
            >
          </li>
          <li class="menu__item item">
            <a
              href="#"
              class="link__last"
              :class="{
                link__last__scroll: btnLink,
                small_window_link: smallWindowLink,
              }"
              >Try It Out</a
            >
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      scrollDown: false,
      scrollDownn: false,
      scrollUp: false,
      lastScrollTop: 0,
      linkScroll: false,
      btnLink: false,
      smallWindowLink: false,
      isOpenMobMenu: false,
    };
  },
  methods: {
    scrollFromStart() {
      if (window.scrollY > 140) {
        this.scrollDown = true;
        this.scrollDownn = true;
        this.linkScroll = true;
        this.btnLink = true;
      } else {
        this.scrollDown = false;
        this.scrollDownn = false;
        this.scrollUp = false;
        this.linkScroll = false;
        this.btnLink = false;
      }
    },
    scrollToTop() {
      let top = window.pageYOffset;
      if (this.lastScrollTop > top && top > 140) {
        this.scrollDownn = false;
        this.scrollDown = false;
        this.scrollUp = true;
      }
      this.lastScrollTop = top;
    },
    scroll() {
      this.scrollFromStart();
      this.scrollToTop();
    },
    smallLinks() {
      window.innerWidth < 768
        ? (this.smallWindowLink = true)
        : (this.smallWindowLink = false);
    },
    mobMenu() {
      this.isOpenMobMenu = !this.isOpenMobMenu;
      document.body.classList.toggle("open");
    },
  },
  created() {
    window.addEventListener("scroll", this.scroll);
    window.addEventListener("resize", this.smallLinks);
  },
  unmounted() {
    window.removeEventListener("scroll", this.scroll);
    window.removeEventListener("resize", this.smallLinks);
  },
};
</script>

<style lang="scss">
@import url("../assets/css/hamburger.min.css");

$color_dark: #1b1c1f;
$color_light: #fff;

.header__container {
  width: 90%;
  max-width: 1170px;
  margin: 0 auto;
  height: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: relative;
}
.header__line {
  &::after {
    content: "";
    width: 100%;
    height: 1px;
    position: absolute;
    left: 0;
    bottom: 0;
    z-index: 20;
    background-color: $color_light;
    @media screen and (max-width: 930px) {
      display: none;
    }
  }
}

/* Header Top */

.header__top {
  width: 100%;
  height: 40px;
  background: url("~@/assets/images/Texture.png") #181a1d;
  background-repeat: no-repeat;
  position: fixed;
  left: 0;
  top: 0;
  z-index: 996;
}
.header__top_non {
  top: -40px;
  transition: all 0.2s ease-out;
}
.nav__list {
  display: flex;
  align-items: center;
  height: 100%;
  .nav__item {
    height: 100%;
  }

  .nav__link {
    display: flex;
    align-items: center;
    height: 100%;
    padding: 0 20px;
    color: rgb(201, 200, 200);
    font-size: 14px;
    font-weight: 500;

    &:hover {
      background-color: #111010;
    }
  }
}

.nav__bar {
  display: flex;

  select {
    font-family: "Gilroy";
    font-size: 12px;
    font-weight: 700;
    margin-right: 20px;
    border: none;
    background-color: transparent;
    color: #fff;
    cursor: pointer;
    outline: none;

    option {
      background-color: $color_dark;
      border: 1px solid $color_dark;
      color: $color_light;
    }
  }
  .menu__btn_link {
    display: flex;
    align-items: center;
  }
}

/* Mobile Menu */

.hamburger {
  display: none;
}

@media screen and (max-width: 768px) {
  .nav__list {
    display: none;
  }
  .hamburger {
    display: block;
  }
}

#mobile_menu_block {
  position: fixed;
  left: -110%;
  top: 0;
  height: 100%;
  width: 100%;
  padding-top: 60px;
  transition: all 0.2s ease;
  background-color: #232323;
  z-index: 995;
}

.open #mobile_menu_block {
  left: 0;
}

.mobile_menu {
  li {
    text-align: center;
    a {
      display: inline-block;
      padding: 15px;
      font-size: 20px;
      color: $color_light;
      width: 100%;

      &:hover {
        background-color: rgb(33, 33, 46);
        color: rgb(90, 89, 89);
      }
    }
  }
}

/* Header Bottom */

.header__bottom {
  width: 100%;
  height: 100px;
  position: fixed;
  left: 0;
  top: 40px;
  overflow: auto;
  white-space: nowrap;
  z-index: 990;
  transition: all 0.2s ease-out;
}
.header__bottom_down {
  background-color: $color_light;
  top: 0;
  color: #000;
}
.header__bottom_up {
  background-color: $color_light;
  top: 40;
  color: #000;
  transition: all 0.2s ease-out;
}

.logo {
  margin-right: 40px;
  &__name {
    font-size: 40px;
    font-weight: 600;
    color: $color_light;
  }
  .link__scroll {
    color: $color_dark;
  }
}
.menu__list {
  display: flex;

  .menu__item {
    position: relative;
    margin-right: 40px;
    &:last-child {
      margin-right: 0;
    }
    .item__link {
      font-family: "Gilroy";
      font-size: 15px;
      font-weight: 500;
      color: $color_light;
      text-decoration: none;

      &::after {
        content: "";
        display: block;
        width: 100%;
        height: 3px;
        background-color: $color_light;
        position: absolute;
        left: 0;
        bottom: -39px;
        z-index: 22;
        transform: scaleX(0);
        transform-origin: left;
      }
      &:hover {
        &::after {
          transform: scaleX(1);
          transition: all ease 0.2s;
        }
      }
    }
    .link__scroll {
      color: $color_dark;
      &::after {
        content: "";
        display: block;
        width: 100%;
        height: 3px;
        background-color: $color_dark;
        position: absolute;
        left: 0;
        bottom: -39px;
        z-index: 21;
        transform: scaleX(0);
        transform-origin: left;
      }
      &:hover {
        &::after {
          transform: scaleX(1);
          transition: all ease 0.2s;
        }
      }
    }
    .link__last {
      font-family: "Gilroy";
      font-size: 16px;
      font-weight: 700;
      color: $color_light;
      border: 3px solid $color_light;
      border-radius: 6px;
      padding: 10px 30px;
      text-transform: uppercase;

      &:hover {
        color: $color_dark;
        background-color: $color_light;
      }
      &:active {
        color: $color_dark;
        background-color: rgb(155, 155, 155);
      }
    }
    .link__last__scroll {
      color: $color_dark;
      border: 3px solid $color_dark;

      &:hover {
        color: $color_light;
        background-color: $color_dark;
      }
      &:active {
        color: $color_light;
        background-color: rgb(75, 75, 75);
      }
    }
    .small_window_link {
      font-size: 15px;
      font-weight: 500;
      text-transform: none;
      font-weight: 500;
      padding: 10px 20px;
      border: 1px solid rgb(121, 121, 121);
      border-radius: 24px;
    }
  }
}
</style>