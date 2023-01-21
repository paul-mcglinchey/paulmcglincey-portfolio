<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HomeTitle from './components/HomeTitle.vue'
import './index.css';
</script>

<template>
  <header>

    <div class="wrapper">
      <HomeTitle />

      <nav>
        <RouterLink to="/">Home</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>
