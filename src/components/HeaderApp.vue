<template>
  <section class="header">
    <div class="header__wrap" id="menu">
      <nav>
        <transition name="fade" mode="out-in">
          <div
            id="burger"
            :class="{ active: isBurgerActive }"
            @click.prevent="toggle"
          >
            <slot>
              <button
                @click="show = !show"
                type="button"
                class="burger-button"
                title="Menu"
              >
                <span class="burger-bar burger-bar--1"></span>
                <span class="burger-bar burger-bar--2"></span>
                <span class="burger-bar burger-bar--3"></span>
              </button>
            </slot>
          </div>
        </transition>
        <div class="sidebar">
          <!-- <div class="sidebar-backdrop" v-if="show"></div> -->
          <transition name="slide">
            <div v-show="show" class="sidebar-panel">
              <ul class="sidebar-panel__list">
                <li class="sidebar-panel__list-point">
                  <a href="#">Главная</a>
                </li>
                <li class="sidebar-panel__list-point">
                  <a href="#">Статус</a>
                </li>
                <li class="sidebar-panel__list-point">
                  <a href="#">Настройки</a>
                </li>
              </ul>
            </div>
          </transition>
        </div>
      </nav>
    </div>
  </section>
</template>
<script>
export default {
  data: () => ({
    isBurgerActive: false,
    show: false,
  }),
  methods: {
    toggle() {
      this.isBurgerActive = !this.isBurgerActive;
    },
  },
};
</script>

<style scoped>
li {
  list-style-type: none;
}
.header {
  background-color: #043873;
  padding: 10px;
}

.burger-button {
  position: relative;
  height: 30px;
  width: 32px;
  display: block;
  z-index: 999;
  border: 0;
  border-radius: 0;
  background-color: transparent;
  pointer-events: all;
  transition: transform 0.6s cubic-bezier(0.165, 0.84, 0.44, 1);
}

.burger-bar {
  background-color: #fff;
  position: absolute;
  top: 50%;
  right: 6px;
  left: 6px;
  height: 2px;
  width: auto;
  margin-top: -1px;
  transition: transform 0.6s cubic-bezier(0.165, 0.84, 0.44, 1),
    opacity 0.3s cubic-bezier(0.165, 0.84, 0.44, 1),
    background-color 0.6s cubic-bezier(0.165, 0.84, 0.44, 1);
}

.burger-bar--1 {
  -webkit-transform: translateY(-6px);
  transform: translateY(-6px);
}

.burger-bar--2 {
  transform-origin: 100% 50%;
  transform: scaleX(0.8);
}

.burger-button:hover .burger-bar--2 {
  transform: scaleX(1);
}

.no-touchevents .burger-bar--2:hover {
  transform: scaleX(1);
}

.burger-bar--3 {
  transform: translateY(6px);
}

#burger.active .burger-button {
  transform: rotate(-180deg);
}

#burger.active .burger-bar--1 {
  transform: rotate(45deg);
}

#burger.active .burger-bar--2 {
  opacity: 0;
}

#burger.active .burger-bar--3 {
  transform: rotate(-45deg);
}

.slide-enter-active,
.slide-leave-active {
  transition: transform 0.2s ease;
}

.slide-enter-from,
.slide-leave-to {
  transform: translateX(-100%);
}

.sidebar-backdrop {
  background-color: rgba(0, 0, 0, 0.5);
  width: 100vw;
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
  cursor: pointer;
}

.sidebar-panel {
  overflow-y: auto;
  background-color: #043873;
  position: fixed;
  left: 0;
  top: 50px;
  height: 100vh;
  z-index: 999;
  padding: 3rem 20px 2rem 20px;
  width: 265px;
}

.sidebar-panel__list-point {
  padding-top: 10px;
}

.sidebar-panel__list-point:first-child {
  padding-top: 0px;
}

.sidebar-panel__list-point a {
  color: #fff;
  text-decoration: none;
  font-size: 20px;
}
</style>
