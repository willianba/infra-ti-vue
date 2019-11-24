<template>
  <div>
    <NavBar @file-upload="showMessage" />
    <MessageBar
      :error="error"
      :message="message"
      @clear-message="clearMessage"
    />
    <ImagesList />
  </div>
</template>

<script>
import ImagesList from "@/components/ImagesList";
import MessageBar from "@/components/MessageBar";
import NavBar from "@/components/NavBar";

export default {
  name: "Home",
  components: {
    ImagesList,
    MessageBar,
    NavBar
  },
  data() {
    return {
      error: "",
      message: ""
    };
  },
  methods: {
    clearMessage() {
      this.error = false;
      this.message = "";
    },
    showMessage(error, message) {
      this.error = error;
      this.message = message;
    }
  }
};
</script>
