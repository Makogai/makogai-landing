<template>
  <div class="about">
    <h1>This is blog page</h1>
    <div v-if="loading" class="loading-container">
      <div class="loader"></div>
    </div>
    <p v-for="el in data" :key="el.id">
      <hello-world
        :title="el.title"
        :image="el.post_image"
        :short_content="el.short_content"
        :id="el.id"
        :slug="el.slug"
        :content="el.content"
      ></hello-world>
    </p>
  </div>
</template>
<script>
import HelloWorld from "../components/HelloWorld.vue";
export default {
  data: () => ({
    data: null,
    loading: false,
    prod_api: "http://mare.rf.gd/aniblog/api/",
    dev_api: "http://127.0.0.1:8001/api/",
  }),
  components: {
    HelloWorld,
  },
  mounted() {
    this.loading = true;
    this.axios.get(this.prod_api + "posts").then((response) => {
      this.data = response.data;
      this.loading = false;
    });
    console.log(this.data);
  },
};
</script>
<style scoped>
.loading-container {
  height: 100vh;
  width: 100%;
  background-color: rgb(255, 255, 255);
}
.loader {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  border: 16px solid #f3f3f3;
  border-top: 16px solid #3498db;
  border-radius: 50%;
  width: 36px;
  height: 36px;
  animation: spin 2s linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
