<template>
  <!-- BEGIN: Left Aside -->
  <!--
    <button class="m-aside-left-close  m-aside-left-close--skin-dark " id="m_aside_left_close_btn">
    <i class="la la-close"></i>
    </button>
    -->
  <div id="m_aside_left" class="m-grid__item m-aside-left m-aside-left--skin-dark ">
    <!-- BEGIN: Aside Menu -->
    <div 
      v-bind:class="{ view_tablet: isTablet() }"
      id="m_ver_menu" 
      class="m-aside-menu m-aside-menu--skin-dark m-aside-menu--submenu-skin-dark" 
      m-menu-vertical="1"
      m-menu-scrollable="1" m-menu-dropdown-timeout="500"  
      style="position: relative;">
      <ul class="m-menu__nav  m-menu__nav--dropdown-submenu-arrow ">
        <li class="m-menu__item  m-menu__item--active" aria-haspopup="true" >
          <a  href="index.html" class="m-menu__link ">
          <i class="m-menu__link-icon flaticon-line-graph"></i>
          <span class="m-menu__link-title">
          <span class="m-menu__link-wrap">
          <span class="m-menu__link-text">
          Dashboard
          </span>
          <span class="m-menu__link-badge">
          <span class="m-badge m-badge--danger">
          2
          </span>
          </span>
          </span>
          </span>
          </a>
        </li>
        <li class="m-menu__section ">
          <h4 class="m-menu__section-text">
            Components
          </h4>
          <i class="m-menu__section-icon flaticon-more-v3"></i>
        </li>
        <li class="m-menu__item  m-menu__item--submenu">
          <a  v-on:click.prevent="toggleMenu" class="m-menu__link m-menu__toggle">
            <i class="m-menu__link-icon flaticon-layers"></i>
              <span class="m-menu__link-text">
              Base
              </span>
            <i class="m-menu__ver-arrow la la-angle-right"></i>
          </a>
          <div class="m-menu__submenu ">
            <span class="m-menu__arrow"></span>
            <ul class="m-menu__subnav">
              <li class="m-menu__item  m-menu__item--parent" aria-haspopup="true">
                <span class="m-menu__link">
                <span class="m-menu__link-text">
                Base
                </span>
                </span>
              </li>
              <li class="m-menu__item " aria-haspopup="true" >
                <a  href="components/base/state.html" class="m-menu__link ">
                <i class="m-menu__link-bullet m-menu__link-bullet--dot">
                <span></span>
                </i>
                <span class="m-menu__link-text">
                State Colors
                </span>
                </a>
              </li>
            </ul>
          </div>
        </li>
      </ul>
    </div>
    <!-- END: Aside Menu -->
  </div>
  <!-- END: Left Aside -->
</template>

<script>
// Begin::Component
export default {
  name: "LeftAsideComponent",
  methods: {
    isTablet() {
      // console.log(this.$store.state.global.window_data.window_width);
      return this.$store.state.global.window_data.window_width < 1025
        ? true
        : false;
    },
    toggleMenu: function(event) {
      //  m-menu__item--open
      console.log(event.target);
    }
  },
  created() {
    // We use eventlistener because vue has no event of its own for resizing and scrolling
    window.addEventListener("resize", this.isTablet);
  }
};
// Begin::Component
</script>
<style scoped lang="scss">
.view_tablet {
  margin-top: 30px;
}
</style>