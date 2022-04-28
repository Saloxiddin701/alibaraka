<template>
  <header class="header">
    <div class="container">
      <nav class="navbar" :class="{'scrolled-nav' : scrollPosition}">
        <div class="logo">
          <img src="../assets/images/ali.png" alt=""/>
        </div>
        <ul class="list" v-show="!mobile">
          <li>
            <router-link to="{ name: '/' }">Products</router-link>
          </li>
          <li>
            <router-link to="{ name: '/products' }">About Us</router-link>
          </li>
          <li>
            <router-link :to="{ name: '' }">Blog</router-link>
          </li>
          <li>
            <router-link :to="{ name: '' }">Contact</router-link>
          </li>
        </ul>
        <div class="phone">
          <i class="fa fa-phone"></i>
          <div class="number">
            <h1>95-004-80-90</h1>
            <h1>94-641-40-00</h1>
          </div>
        </div>
        <div class="icon">
          <i v-show="mobile" @click="toggleMobileNav" :class="{ 'icon-active' : mobileNav }" class="fa fa-bars"></i>
        </div>
        <transition name="mobile-nav">
          <ul v-show="mobileNav" class="dropdown-nav">
            <li>
              <router-link class="link" :to="{ name: '' }">Products</router-link>
            </li>
            <li>
              <router-link class="link" :to="{ name: '' }">About Us</router-link>
            </li>
            <li>
              <router-link class="link" :to="{ name: '' }">Blog</router-link>
            </li>
            <li>
              <router-link class="link" :to="{ name: '' }">Contact</router-link>
            </li>

            <div class="phone" v-show="mobileNav">
              <i class="fa fa-phone"></i>
              <div class="number">
                <h1>95-004-80-90</h1>
                <h1>94-641-40-00</h1>
              </div>
            </div>
          </ul>
        </transition>
      </nav>
      <div class="item">
        <div class="left">
          <h1>ВСЕ ДЛЯ ТЕПЛИЦ</h1>
          <p>
            Here will be brief information about our company and some of advantages of our offers. Here will be brief
            information about our company.
          </p>
          <button class="btn">EXPLORE <i class="fa fa-arrow-right"></i></button>
        </div>
        <div class="right">
          <div class="line1">
            <div class="line2">
              <div class="elapse">
                <i class="fa fa-play"></i>
              </div>
            </div>
          </div>
        </div>
      </div>

    </div>
  </header>
  <div class="bottom1">
    <img src="../assets/images/bottom-img-removebg-preview.png" alt="" class="img">
  </div>
</template>


<script>
export default {
  name: "Home",
  data() {
    return {
      scrolledNav: null,
      mobile: null,
      mobileNav: null,
      windowWidth: null
    }
  },
  created() {
    window.addEventListener('resize', this.checkScreen)
    this.checkScreen()
  },
  mounted() {
    window.addEventListener('scroll', this.updateScroll)
  },
  methods: {
    toggleMobileNav() {
      this.mobileNav = !this.mobileNav
    },
    updateScroll() {
      const scrollPosition = window.scrollY
      if (scrollPosition > 50) {
        this.scrolledNav = true
        return;
      }
      this.scrolledNav = false
    },
    checkScreen() {
      this.windowWidth = window.innerWidth
      if (this.windowWidth <= 790) {
        this.mobile = true
        return;
      }
      this.mobile = false
      this.mobileNav = false
      return;
    }
  }
};
</script>

<style>
</style>