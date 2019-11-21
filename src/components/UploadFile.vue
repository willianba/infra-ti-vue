<template>
  <div class="file is-primary is-small">
    <label class="file-label">
      <input
        class="file-input"
        type="file"
        name="file"
        @change="handleFileUpload"
      />
      <span class="file-cta">
        <span class="file-label">
          New post
        </span>
      </span>
    </label>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "UploadFile",
  data() {
    return {
      error: false,
      file: "",
      message: ""
    };
  },
  methods: {
    async handleFileUpload(event) {
      this.file = event.target.files[0];
      const formData = new FormData();
      formData.append("upload", this.file);
      try {
        await axios.post("http://localhost:3000/upload-file", formData);
        this.message = "File uploaded";
        this.error = false;
        this.file = "";
      } catch (err) {
        this.message = "Something went wrong";
        this.error = true;
      } finally {
        this.$emit("file-upload", this.error, this.message);
      }
    }
  }
};
</script>
