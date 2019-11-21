<template>
  <div
    v-if="message"
    class="message is-small"
    :class="{ 'is-danger': error, 'is-success': !error }"
    style="margin: 10px"
  >
    <div class="message-header">
      <p>{{ error ? "Failed" : "Success" }}</p>
      <button
        class="delete"
        @click="
          message = '';
          error = false;
        "
      ></button>
    </div>
    <div class="message-body">{{ message }}</div>
  </div>
</template>

<script>
export default {
  name: "MessageBar",
  props: {
    error: {
      type: Boolean,
      required: true
    },
    message: {
      type: String,
      required: true
    }
  }
};
</script>
