<template>
  <div class="radio-wrap">
    <div class="radio-wrap-content">
      <input type="radio" value="Андрей Б" v-model="picked" />
      <label class="executor" for="one">Андрей Б</label>
    </div>
    <div class="radio-wrap-content">
      <input type="radio" value="Андрей В" v-model="picked" />
      <label class="executor" for="two">Андрей В</label>
    </div>
    <div class="radio-wrap-content">
      <input type="radio" value="Максим" v-model="picked" />
      <label class="executor" for="three">Максим</label>
    </div>
    <div class="radio-wrap-content">
      <input type="radio" value="Саша" v-model="picked" />
      <label class="executor" for="four">Саша</label>
    </div>
    <div class="radio-wrap-content">
      <input type="radio" value="Лёша" v-model="picked" />
      <label class="executor" for="five">Лёша</label>
    </div>
    <div class="radio-wrap-content">
      <input type="radio" value="Даша" v-model="picked" />
      <label class="executor" for="six">Даша</label>
    </div>

    <div class="conclusion">Выбрано: {{ picked }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      picked: "",
    };
  },
};
</script>

<style scoped>
.radio-wrap {
  padding: 0 40px;
}
.conclusion {
  background-color: #3cb371;
  color: #fff;
  padding: 20px;
  margin-top: 20px;
}
.radio-wrap-content {
  padding-top: 20px;
}
.executor {
  padding-left: 10px;
}
</style>
