<template>
  <div>
    <input
      type="checkbox"
      id="main-navigation-toggle"
      class="btn btn--close"
      title="Toggle main navigation"
    />
    <label for="main-navigation-toggle">
      <span></span>
    </label>
    <nav id="main-navigation" class="nav-main">
      <ul class="menu">
        <li class="menu__item">
          <router-link class="menu__link" to="/" v-on:click="closeNav"
            >Home</router-link
          >
        </li>
        <li class="menu__item">
          <router-link class="menu__link" to="/about" v-on:click="closeNav"
            >About</router-link
          >
        </li>
        <li class="menu__item">
          <router-link class="menu__link" to="/contact" v-on:click="closeNav"
            >Contact</router-link
          >
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  methods: {
    closeNav() {
      document.querySelector("#main-navigation-toggle").click();
      console.log("Clicked close nav");
    },
  },
};
</script>

<style>
@import "../assets/navbar/style.css";
</style>
