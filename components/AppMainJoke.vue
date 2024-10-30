<script lang="ts" setup>
// URL для запроса шутки с JokeAPI
const apiUrl = 'https://v2.jokeapi.dev/joke/Programming';

interface JokeResponse {
  joke?: string;
  setup?: string;
  delivery?: string;
}

// Использование useFetch для выполнения запроса
const { data: jokeData, error } = await useFetch<JokeResponse>(apiUrl);

// Извлечение шутки из данных
const joke = computed(
  () =>
    jokeData.value?.joke ||
    jokeData.value?.setup + ' ' + jokeData.value?.delivery
);
</script>

<template>
  <div>
    <h1>Здесь будет главный анекдот</h1>
    <p v-if="joke">{{ joke }}</p>
    <p v-else-if="error">Ошибка при загрузке шутки</p>
    <p v-else>Загрузка...</p>
  </div>
</template>
