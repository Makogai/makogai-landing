<template>
  <Navbar />
  <main class="page-container">
    <router-view />
  <Version :version="version" :msg="msg"/>
  </main>
</template>
<script>
import Navbar from "@/components/Navbar.vue";
import Version from "@/components/Version.vue";
export default {
    data: () => ({
    version: "0.0.2",
    msg: "Dev-Alpha",
  }),
  components: {
    Navbar,
    Version,
  },
};
</script>
<style>
.version-conatiner{
    position: fixed;
    bottom: 0;
    left:0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
* {
  margin: 0;
}
</style>
