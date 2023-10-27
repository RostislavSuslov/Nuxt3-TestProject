<template>
    <div>
      <UiBreadcrumbs />
      <h1 class="text-[72px]">Contacts</h1>
      <p>Contacts page, Contacts page, Contacts page, Contacts page, Contacts page, Contacts page,</p>
      <div>
        <!-- SSR Teleport -->
        <Teleport to="body">
          SSR Teleport
        </Teleport>
  
        <!-- Client Teleport -->
        <ClientOnly>
          <Teleport to="body">
            <div>
              Hello from a client-side teleport!
            </div>
          </Teleport>
        </ClientOnly>
  
       
        <UiModal/>
      </div>
    </div>
</template>
  
<script lang="ts" setup>

</script>
