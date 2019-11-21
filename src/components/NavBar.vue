<template>
  <nav class="navbar is-dark is-fixed-top" role="navigation">
    <span class="navbar-item">
      <img src="@/assets/navbar-logo.png" />
    </span>
    <div class="navbar-item">
      <UploadFile @file-upload="sendToHome" />
    </div>
  </nav>
</template>

<script>
import UploadFile from "./UploadFile";

export default {
  name: "NavBar",
  components: {
    UploadFile
  },
  methods: {
    sendToHome(error, message) {
      this.$emit("file-upload", error, message);
    }
  }
};
</script>
