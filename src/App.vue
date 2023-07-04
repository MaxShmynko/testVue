<template>
  <HeaderApp />
  <sliderApp />
  <div class="wrap">
    <!-- <sliderApp /> -->
    <headingsApp cssClass="title__forms" title="Форма заполнения" />
    <div class="container">
      <CompletionApp
        cssClass="form-filling"
        title="Введите ваши данные"
        name="Имя"
        secondName="E-mail"
      />
      <CompletionApp
        cssClass="form-filling-two"
        title="Дополнительные данные"
        name="Адрес"
        secondName="Телефон"
      />
    </div>
    <headingsApp cssClass="title__forms" title="Навыки" />
    <div class="cards">
      <cardsApp
        cssClass="cards__wrap-blue"
        title="Html"
        content="95%"
        secondTitle="Знаю"
      />
      <cardsApp
        cssClass="cards__wrap-white"
        title="CSS"
        content="90%"
        secondTitle="Знаю"
      />
      <cardsApp
        cssClass="cards__wrap-yellow"
        title="JS"
        content="30%"
        secondTitle="Хочу знать"
      />
      <cardsApp
        cssClass="cards__wrap-green"
        title="Vue 3"
        content="10%"
        secondTitle="Хочу знать"
      />
    </div>
    <div class="radio">
      <headingsApp cssClass="title__forms" title="Исполнитель" />
      <radioApp />
    </div>
  </div>
</template>

<script>
import HeaderApp from "./components/HeaderApp.vue";
import CompletionApp from "./components/CompletionApp.vue";
import cardsApp from "./components/cardsApp.vue";
import radioApp from "./components/radioApp.vue";
import sliderApp from "./components/sliderApp.vue";
import headingsApp from "@/components/additionally/headingsApp.vue";

export default {
  components: {
    HeaderApp,
    CompletionApp,
    cardsApp,
    headingsApp,
    radioApp,
    sliderApp,
  },
};
</script>

<style>
* {
  padding: 0px;
  margin: 0px;
  border: none;
}

body {
  border: 0;
  margin: 0;
  padding: 0;
}

.logo {
  align-self: center;
  color: #fff;
  font-weight: bold;
  font-family: "Lato";
}

.main-nav {
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 0.8rem;
}

ul.sidebar-panel-nav {
  list-style-type: none;
}

ul.sidebar-panel-nav > li > a {
  color: #fff;
  text-decoration: none;
  font-size: 1.5rem;
  display: block;
  padding-bottom: 0.5em;
}

.wrap {
  width: 1200px;
  margin: 0 auto;
}

.container {
  display: flex;
  justify-content: space-around;
}
.cards {
  display: flex;
  justify-content: space-evenly;
  margin-top: 50px;
}
</style>
