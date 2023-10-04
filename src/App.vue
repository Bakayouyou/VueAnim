<script setup>

</script>

<template>
<div>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view v-slot="{ Component }">
    <transition name="fade">
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
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}


</style>
