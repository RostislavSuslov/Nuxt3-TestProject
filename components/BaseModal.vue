<script>
export default {
  data () {
    return {
      open: false
    }
  }
}
</script>

<template>
    <div>
        <button class="bg-orange-500 text-white inline-flex border px-12 py-3 cursor-pointer rounded-[5px]" @click="open = true">
            Open Modal
          </button>
          <Teleport to="body">
            <div v-if="open" class="modal border p-10 bg-blue-50 text-center">
              <h3 class="text-[24px] mb-5">Hello from the modal!</h3>
              <p class="mb-4">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Illum unde,   optio soluta recusandae reiciendis fuga ratione esse beatae corporis dolore neque magni consequatur facilis!</p>
              <div class="inline-flex border px-12 py-3 cursor-pointer rounded-[5px] bg-red-300" @click="open = false">
                Close
              </div>
            </div>
          </Teleport>
    </div>
</template>

<style scoped>
.modal {
  position: fixed;
  z-index: 999;
  top: 20%;
  left: 50%;
  width: 300px;
  margin-left: -150px;
}
</style>
