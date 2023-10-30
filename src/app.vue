<template>
    <div class="container mx-auto px-3">
        <nav class="flex align-center gap-4 border p-4 my-2">
            <NuxtLink to="/">
                Home
            </NuxtLink>
           
            <NuxtLink to="/users">
                Users
            </NuxtLink>
            <NuxtLink to="/contacts">
                Contacts
            </NuxtLink>
            <NuxtLink to="/catalog/">
                Catalog
            </NuxtLink>
            <NuxtLink to="/catalog/category">
                Category
            </NuxtLink>
        </nav>
        <!-- <NuxtLayout>
            <NuxtPage class="border p-4" />
        </NuxtLayout> -->
      
        <div class="h-full">
            <nuxt-layout>
            
            <nuxt-loading-indicator />
            <nuxt-page/>
            
            </nuxt-layout>
        </div>
      
        <div class="flex gap-5 my-4 p-4 border">
            <button
                class="inline-flex h-12 items-center justify-center gap-2 whitespace-nowrap rounded bg-emerald-500 px-6 text-sm font-medium tracking-wide text-white transition duration-300 hover:bg-emerald-600 focus:bg-emerald-700 focus-visible:outline-none"
                @click="showError">
                <span>
                    Trigger fatal error
                </span>
            </button>
            <button
                class="inline-flex h-12 items-center justify-center gap-2 whitespace-nowrap rounded bg-red-500 px-6 text-sm font-medium tracking-wide text-white transition duration-300 hover:bg-emerald-600 focus:bg-emerald-700 focus-visible:outline-none"
                @click="triggerError">
                <span>
                    Trigger non-fatal error
                </span>
            </button>
        </div>

        <div class="border my-4 p-4">
            <Test message="This is an external JSX component" />
        </div>
        
         <footer class="flex gap-2">
            <button class="border p-2 " @click="setPageLayout('about')">
                about
            </button>
            <button class="border p-2 " @click="setPageLayout('contacts')">
                contacts
            </button>
            <button class="border p-2 " @click="setPageLayout('catalog')">
                catalog/catalog
            </button>
            <button class="border p-2 " @click="setPageLayout('catalog/category/category')">
                /catalog/category/category
            </button>
            <button class="border p-2 " @click="setPageLayout(false)">
              Remove layout
            </button>
        </footer> 
    </div>
</template>
<script setup lang="ts">
    import {
        showError
    } from '#app'
    const route = useRoute()

    if ('setup' in route.query) {
        throw new Error('error in setup')
    }
    if ('mounted' in route.query) {
        onMounted(() => {
            throw new Error('error in mounted')
        })
    }

    function triggerError() {
        throw new Error('manually triggered error')
    }


    /**/
    
// function setPageLayout(layout) {
//   const router = useRouter();
//   if (layout) {
//     router.push({ query: { layout } });
//   } else {
//     router.push({ query: {} });
//   }
// }
</script>