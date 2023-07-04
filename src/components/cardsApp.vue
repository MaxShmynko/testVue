<template>
  <div class="cards__wrap">
    <div :class="cssClass">
      <div class="cards__title text">{{ title }}</div>
      <div class="cards__content text">{{ content }}</div>
      <div class="cards__second-title text">{{ secondTitle }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    content: String,
    secondTitle: String,
    cssClass: {},
  },
};
</script>

<style scoped>
.cards__wrap-blue,
.cards__wrap-white,
.cards__wrap-yellow,
.cards__wrap-green {
  background: #043873;
  color: #e6e6e6;
  padding: 20px;
  border-radius: 5px;
  text-align: center;
  width: 217px;
}

.cards__wrap-white {
  background: #fff;
  box-shadow: 10px 5px 5px #043873;
  border: 1px solid #043873;
  color: #000;
}

.cards__wrap-yellow {
  background: #ffff00;
  box-shadow: 10px 5px 5px #043873;
  color: #000;
}
.cards__wrap-green {
  background-color: #3cb371;
}
.text {
  font-size: 25px;
  padding-top: 10px;
}

.text:first-child {
  padding-top: 0px;
}
</style>
