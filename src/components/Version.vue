<template>

      <div class="version-container" style=" position: fixed;
  bottom: 0;
  left: 0;">
    <div class="msg">
      {{ msg }}
    </div>
    <div class="version">
     v {{ version }}
    </div>
      </div>

</template>

<script>
export default {
  props: {
    version: String,
    msg: String,
  },
};
</script>

<style>
@import "../assets/version/style.css";
</style>

