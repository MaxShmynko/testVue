<template>
  <div class="form-input">
    <input class="input-text" :type="type" :name="name" :id="name" />
  </div>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      default: "text",
    },
    name: {
      type: String,
      required: "true",
    },
    secondName: {
      type: String,
      required: "true",
    },
  },
};
</script>

<style scoped>
.input-text {
  padding: 10px 15px;
  border-width: 0;
  background: #e6e6e6;
  outline: none;
  margin: 0;
  width: 93%;
  margin-top: 10px;
}
</style>
