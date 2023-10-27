<template>
  <div>
    <UiBreadcrumbs />
    <h1 class="text-[72px]">Home</h1>
    <div class="flex-1">
      <div class="flex flex-col lg:flex-row lg:items-center lg:justify-between">
        <h1 class="text-3xl sm:text-4xl font-bold text-gray-900 dark:text-white tracking-tight">
          State Management
        </h1>
      </div>
      <p class="mt-4 text-lg text-gray-500 dark:text-gray-400">
        This example shows how to use the `useState` composable to create a reactive and SSR-friendly shared
        state across components.</p>
    </div>

    <div class="p-4 my-4">
      <p>Counter: {{ counter }}</p>
      <div class="flex gap-5 my-4 p-4 border">
        <button
          class="inline-flex h-12 items-center justify-center gap-2 whitespace-nowrap rounded bg-emerald-500 px-6 text-sm font-medium tracking-wide text-white transition duration-300 hover:bg-emerald-600 focus:bg-emerald-700 focus-visible:outline-none"
          @click="counter--">-</button>
        <button
          class="inline-flex h-12 items-center justify-center gap-2 whitespace-nowrap rounded bg-red-500 px-6 text-sm font-medium tracking-wide text-white transition duration-300 hover:bg-emerald-600 focus:bg-emerald-700 focus-visible:outline-none"
          @click="counter++">+</button>
      </div>
      <p>Same Counter: {{ sameCounter }}</p>
    </div>
  </div>
</template>
<script setup>

  const counter = useState('counter', () => Math.round(Math.random() * 1000))
  const sameCounter = useState('counter')
</script>