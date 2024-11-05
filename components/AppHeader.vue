<script setup lang="ts">
import { pageConfig } from '~/configs/pages.config';
</script>

<template>
  <header class="app-header">
    <h1>Cервис «Анекдотопад»</h1>
    <nav class="app-header-nav">
      <ul>
        <li>
          <NuxtLink :to="pageConfig.home">Анекдот дня</NuxtLink>
        </li>
        <li>
          <NuxtLink :to="pageConfig.authorAnecdote">Авторский анекдот</NuxtLink>
        </li>
        <li>
          <NuxtLink :to="pageConfig.addOwnAnecdote">Добавить анекдот</NuxtLink>
        </li>
        <li>
          <NuxtLink :to="pageConfig.usersAnecdotes">Анекдоты пользователей</NuxtLink>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style scoped lang="scss">
.app-header {
  display: flex;
  min-height: 100px;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  outline: 3px solid red;

  h1 {
    text-align: center;
  }
}

.app-header-nav {
  display: flex;

  ul {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    align-items: center;
  }

  li {
    font-size: 18px;
    list-style-type: none;
  }
}
</style>
