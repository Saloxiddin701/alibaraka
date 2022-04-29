<template>
  <nav class="navbar" :class="{'onScroll' : !view.topOfPage}">
    <div class="logo">
      <img src="../assets/images/ali.png" alt=""/>
    </div>
    <ul class="list" v-show="!mobile">
      <li>
        <a href="#product">Products</a>
      </li>
      <li>
        <a href="#about">About Us</a>
      </li>
      <li>
        <a href="#blog">Blog</a>
      </li>
      <li>
        <a href="#contact">Contact</a>
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
          <a href="#product">Products</a>
        </li>
        <li>
          <a href="#about">About Us</a>
        </li>
        <li>
          <a href="#blog">Blog</a>
        </li>
        <li>
          <a href="#contact">Contact</a>
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
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      scrolledNav: null,
      mobile: null,
      mobileNav: null,
      windowWidth: null,
      view: {
        topOfPage: true
      }
    }
  },
  created() {
    window.addEventListener('resize', this.checkScreen)
    this.checkScreen()
  },
  mounted() {
    window.addEventListener('scroll', this.hundleScroll)
  },
  methods: {
    hundleScroll() {
      if(window.pageYOffset > 0) {
        this.view.topOfPage = false
      } else {
        if(!this.view.topOfPage) {
          this.view.topOfPage = true
        }
      }
    },
    toggleMobileNav() {
      this.mobileNav = !this.mobileNav
    },
    updateScroll() {
      const scrollPosition = window.scrollY
      if (scrollPosition > 20) {
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
}
</script>

<style scoped>

</style>