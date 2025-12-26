<template>
  <div class="bg-gray-800 p-4">
    <div class="container mx-auto">
      <div class="flex justify-between items-center">
        <div class="text-white text-lg font-bold">My Portfolio</div>

        <div class="hidden md:flex space-x-6">
          <a href="#hero" class="text-gray-300 hover:text-white transition px-4 ">Home</a>
          <a href="#projects" class="text-gray-300 hover:text-white transition px-4">Projects</a>
          <a href="#volunteer" class="text-gray-300 hover:text-white transition px-4">Volunteer</a>
          <a href="#contact" class="text-gray-300 hover:text-white transition px-4">Contact</a>
        </div>

        <button
            @click="isOpen = !isOpen"
            class="md:hidden text-gray-300 focus:outline-none"
        >
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
            />
            </svg>
        </button>



      </div>
    </div>

    <div v-if="isOpen" class="md:hidden flex flex-col space-y-3 bg-gray-700 p-4 rounded mt-2">
        <a href="#hero" class="hover:text-white ">Home</a>
        <a href="#projects" class="hover:text-white ">Projects</a>
        <a href="#volunteer" class="hover:text-white ">Volunteer</a>
        <a href="#contact" class="hover:text-white ">Contact</a>
    </div>
    
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { ref } from 'vue'

export default defineComponent({
  name: 'NavBar',
  setup() {
    const isOpen = ref(false)
    return { isOpen }
  }
})

</script>
