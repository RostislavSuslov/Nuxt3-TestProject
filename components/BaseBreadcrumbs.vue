<template>
    <div class="text-gray-400">
       {{ route.path }}
    </div>
</template>
<script setup>
const route = useRoute()
</script>