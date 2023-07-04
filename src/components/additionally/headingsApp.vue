<template>
  <div :class="cssClass">
    {{ title }}
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    cssClass: {},
  },
};
</script>

<style scoped>
.title__forms {
  font-size: 30px;
  text-align: center;
  margin-top: 50px;
  font-weight: bold;
}
</style>
