<template>
  <div>
    <h1>Список персонажей:</h1>
    <ul class="flex flex-wrap gap-5 justify-center">
      <li v-for="character in characters" :key="character.id">
        <NuxtLink :to="$route.params.slug">
          <img :src=" character.image" alt="">
          {{ character.name }}
        </NuxtLink>
       
      </li>
    </ul>
  </div>
</template>

<script setup>
const route = useRoute()
const { data: characters, error, loading } = useAsyncData(async () => {
  try {
    const response = await fetch('https://rickandmortyapi.com/api/character')
    const data = await response.json()
    return data.results
  } catch (error) {
    console.error('Произошла ошибка:', error)
  }
})

//rout.params.slug
</script>

<!--
  https://rickandmortyapi.com/api/character
-->