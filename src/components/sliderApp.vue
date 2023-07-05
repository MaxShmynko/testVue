<template>
  <div class="sliderApp">
    <transition name="slide-fade" mode="out-in">
      <!-- <slidsContent :items="slides"/> -->
      <component
        :is="'slidsContent'"
        :key="currentSlide"
        :items="slides[currentSlide]"
      />
    </transition>
  </div>
  <div class="controls">
    <button
      class="button prev"
      @click="prevSlide"
      :class="{ disabled: currentSlide <= 0 }"
    >
      Назад
    </button>
    <button
      class="button next"
      @click="nextSlide"
      :class="{ disabled: currentSlide > 1 }"
    >
      Вперёд
    </button>
  </div>
</template>

<script>
import slidsContent from "@/components/additionally/slidsContent.vue";

export default {
  name: "sliderApp",
  components: {
    slidsContent,
  },
  data() {
    return {
      slides: [
        {
          id: 0,
          img: "https://via.placeholder.com/640x360.png?text=Slide+1",
          title: "Slide 1",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
        },
        {
          id: 1,
          img: "https://via.placeholder.com/640x360.png?text=Slide+2",
          title: "Slide 2",
          description:
            "Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
        },
        {
          id: 2,
          img: "https://via.placeholder.com/640x360.png?text=Slide+3",
          title: "Slide 3",
          description:
            "Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris.",
        },
        {
          id: 3,
          img: "https://via.placeholder.com/640x360.png?text=Slide+4",
          title: "Slide 4",
          description:
            "Duis aute irure dolor in reprehenderit in voluptate velit esse.",
        },
      ],
      currentSlide: 0,
    };
  },
  methods: {
    prevSlide() {
      if (this.currentSlide > 0) {
        this.currentSlide--;
      }
    },
    nextSlide() {
      if (this.currentSlide < this.slides.length - 1) {
        this.currentSlide++;
      }
    },
  },
  props: {
    carousel_data: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style scoped>
.sliderApp {
  height: 530px;
}
.controls {
  position: absolute;
  top: 470px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
}
.button {
  font-size: 24px;
  margin: 0 10px;
  padding: 10px;
  cursor: pointer;
  border-radius: 10px;
}

.prev {
  box-shadow: 10px 5px 5px #043873;
  border: 1px solid #043873;
  background: #fff;
}
.next {
  background: #043873;
  color: #e6e6e6;
  box-shadow: none;
  border: none;
}

.prev:hover {
  background: #3cb371;
  color: #e6e6e6;
  box-shadow: 10px 5px 5px #3cb371;
  border: 1px solid #3cb371;
}
.next:hover {
  background: #3cb371;
  box-shadow: 10px 5px 5px #3cb371;
  border: 1px solid #3cb371;
}
.slide-fade-enter-active {
  transition: all 0.8s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from {
  transform: translateX(-100%);
  opacity: 0;
}
.slide-fade-leave-to {
  transform: translateX(100%);
  opacity: 0;
}
</style>
