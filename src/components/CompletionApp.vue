<template>
  <div :class="cssClass">
    <h1>{{ title }}</h1>
    <div class="form-filling-completion">
      <label>{{ name }}</label>
      <InputApp type="text" />
    </div>
    <div class="form-filling-completion">
      <label>{{ secondName }}</label>
      <InputApp type="text" />
    </div>
    <div
      class="form-filling-completion"
      v-for="item in items"
      :key="item.message"
    >
      <label>{{ item.message }}</label>
      <InputApp type="text" />
    </div>
  </div>
</template>

<script>
import InputApp from "@/components/additionally/InputApp.vue";
export default {
  components: {
    InputApp,
  },
  props: {
    title: String,
    name: String,
    secondName: String,
    cssClass: {},
  },
  data() {
    return {
      items: [{ message: "Foo" }, { message: "Bar" }],
    };
  },
};
</script>

<style scoped>
.form-filling,
.form-filling-two {
  margin-top: 50px;
  width: 500px;
  padding: 20px;
  box-shadow: 10px 5px 5px #043873;
  border: 1px solid #043873;
  border-radius: 10px;
}

.form-filling-two {
  background: #043873;
  color: #e6e6e6;
  box-shadow: none;
  border: none;
}

.form-filling-completion {
  display: flex;
  flex-direction: column;
  margin-top: 15px;
}
</style>
