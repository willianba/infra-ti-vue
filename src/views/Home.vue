<template>
  <div>
    <NavBar @file-upload="showMessage" />
    <MessageBar :error="error" :message="message" />
  </div>
</template>

<script>
import MessageBar from "@/components/MessageBar";
import NavBar from "@/components/NavBar";

export default {
  name: "Home",
  components: {
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
    showMessage(error, message) {
      this.error = error;
      this.message = message;
    }
  }
};
</script>
