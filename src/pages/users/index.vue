<template>
  <div>
    <h1>User list:</h1>
    <ul class="flex flex-wrap gap-5 justify-center">
      <li v-for="character in characters" :key="character.id">
        <NuxtLink :to="/users/ +  character.id">
          <img :src=" character.image" alt="">
          <h3 class="text-[24px]">{{ character.name }}</h3>
        </NuxtLink>
        <pre>
          {{ /users/ +  character.id}}
        </pre>
      </li>
    </ul>
  </div>
</template>

<script setup>
File: /users.vue/;
Url:  /users/;

const route = useRoute()
 

const { data: characters, error, loading } = useAsyncData(async () => {
  try {
    const response = await fetch('https://rickandmortyapi.com/api/character')
    const data = await response.json()
    return data.results
  } catch (error) {
    console.error('Error:', error)
  }
 
})
//rout.params.slug
</script>
