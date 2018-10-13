<template>
  <div id="app">
    <h3>HeroBase Router</h3>
    <h4>
      <router-link class="link" to="/data/characters">
        Meet the Characters
      </router-link> |
      <router-link class="link" to="/data/realms">
        Explore the Realms
      </router-link>
    </h4>
    <router-view></router-view>
  </div>
</template>
