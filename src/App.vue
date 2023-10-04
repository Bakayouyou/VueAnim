<script setup>

import { ref } from 'vue'

const anim = ref('fade')

</script>

<template>
  <div>

    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </nav>

    <div class="check">
      <label>
        <input type="radio" value="fade" name="anim" v-model="anim">Fade
      </label>
      <label>
        <input type="radio" value="slide" name="anim" v-model="anim">slide
      </label>
      <label>
        <input type="radio" value="slide-down" name="anim" v-model="anim">slide-down
      </label>
      <label>
        <input type="radio" value="grow-in" name="anim" v-model="anim">grow-in
      </label>
      <label>
        <input type="radio" value="grow-out" name="anim" v-model="anim">grow-out
      </label>
    </div>

    <router-view v-slot="{ Component }">
      <transition name="fade" mode="out-in">
        <Component :is="Component" />
      </transition>
    </router-view>

  </div>
</template>

<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

main {
  max-width: 768px;
  margin: 0 auto;
  padding: 1rem;
  will-change: opacity, transform;
}

h1 {
  font-size: 2rem;
  margin-bottom: 1rem;
}

p {
  margin-bottom: 1rem;
}

img {
  width: 100%;
  height: auto;
  margin-bottom: 1.5rem;
}

nav {
  display: flex;
  place-content: center;
  place-items: center;
  background: #eee;
  padding: 1rem;
  margin-bottom: 1rem;
}

nav a {
  text-decoration: none;
  color: #333;
  font-weight: bold;
  padding: 0.5rem;
}

nav a:hover,
nav a.router-link-exact-active {
  text-decoration: none;
  color: crimson;
}

.check {
  display: flex;
  place-content: center;
  place-items: center;
  margin-bottom: 1rem;
}
.check label {
  margin-right: 1rem;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease-out;
}
</style>
