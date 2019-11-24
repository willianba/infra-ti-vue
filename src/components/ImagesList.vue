<template>
  <div class="content">
    <figure class="image" v-for="image in images.data" :key="image">
      <img :src="image" class="resized-image" />
    </figure>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "ImagesList",
  data() {
    return {
      images: ""
    };
  },
  methods: {
    async getImages() {
      this.images = await axios.get("http://localhost:3000/");
    }
  },
  mounted() {
    this.getImages();
  }
};
</script>

<style scoped>
.resized-image {
  width: 45%;
  height: auto;
}
</style>
