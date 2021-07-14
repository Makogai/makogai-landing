<template>
  <div class="hello">
    <img :src="image" alt="" />
    <router-link :to="{ path: '/blog/'+ id}"><h6>{{ title }}</h6></router-link>
    <p>{{ short_content }}</p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    title: String,
    content: String,
    short_content: String,
    slug: Number,
    id: Number,
    image: String,
  },
};
</script>
<style scoped>
img {
  width: 90%;
  height: 150px;
  object-fit: cover;
}
.hello{
  background-color: rgb(241, 241, 241);
  margin: 10px auto;
  width: 50%;
  padding: 10px 0;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.116);
}
</style>
