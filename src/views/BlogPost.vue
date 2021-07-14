<template>
  <div>
      <img :src="image" alt="">
    <h2>{{ title }}</h2>
    <p v-html="content"></p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      id: this.$route.params.id,
      title: "",
      content: "",
      image: "",
      prod_api: "http://mare.rf.gd/aniblog/api/",
      dev_api: "http://127.0.0.1:8001/api/",
    };
  },
  mounted() {
    this.axios.get(this.prod_api + "posts/" + this.id).then((response) => {
      this.title = response.data[0].title;
      this.content = response.data[0].content;
      this.image = response.data[0].post_image;
    });
  },
};
</script>

<style scoped>
h2 {
  margin-bottom: 20px;
}
img{
    width: 100%;
}
</style>
