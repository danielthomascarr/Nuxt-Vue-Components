<template>
  <nav class="navbar">
      <div class="navbar-brand">
        <a class="navbar-item" href="/">
          <img src="http://bulma.io/images/bulma-logo.png" alt="Logo">
        </a>
        <!--
    Using the v-on: directive to listen for the click event and toggle the data property showNav. Also, using the v-bind: directive to reactively update the class attribute 'is-active' based on the showNav property.
    -->
        <div class="navbar-burger" @click="showNav = !showNav" :class="{ 'is-active': showNav }">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>
      <!--
    Using the v-bind: directive to reactively update the class attribute 'is-active' based on the showNav property.
    -->
      <div class="navbar-menu" :class="{ 'is-active': showNav }">
        <div class="navbar-end">
          <a class="navbar-item" href="/about">
            About
          </a>
          <a class="navbar-item" href="/path">
            Path
          </a>
          <a class="navbar-item" href="/blog">
            Blog
          </a>
        </div>
      </div>
    </nav>
</template>

<script>

export default {
  data () {
      return {
        showNav: false
      }
    }
  }

</script>

<style>

.navbar-burger {
    color: #d3531a;
}

.navbar-burger:hover {
    background-color: #ffffff;
    color: #d3531a;
    opacity: 0.8;
}

.navbar-burger span {
    height: 3px;
    left: calc(50% - 8px);
    width: 20px;
}

.navbar-burger span:nth-child(1) {
    top: calc(50% - 8px);
}

.navbar-burger span:nth-child(2) {
    top: calc(50% - 2px);
}

.navbar-burger.is-active span:nth-child(1) {
    -webkit-transform: translateY(7px) rotate(45deg);
    transform: translateY(7px) rotate(45deg);
}


</style>


