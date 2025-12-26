<template>
  <section class="py-16 bg-gray-900 text-white">
    <div class="max-w-6xl mx-auto text-center">
      <h2 class="text-4xl font-bold mb-8">My Tech Stack</h2>

      <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-8">
        <div v-for="tech in techStack" :key="tech.name" class="flex flex-col items-center">
          <img :src="tech.icon" :alt="tech.name" class="w-16 h-16 mb-2 object-contain"/>
          <span class="text-lg font-medium">{{ tech.name }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'TechStack',
  setup() {
    const techStack = ref([ 
      { name: 'Vue.js', icon: 'tech_stack/vue.png' },
      { name: 'TypeScript', icon: 'tech_stack/typescript.png' },
      { name: 'JavaScript', icon: 'tech_stack/javascript.png' },
      { name: 'HTML', icon: 'tech_stack/html.png' },
      { name: 'CSS', icon: 'tech_stack/css.png' },
      { name: 'Tailwind CSS', icon: 'tech_stack/tailwind.png' },
      { name: 'Nest.js', icon: 'tech_stack/nest.png' },
      { name: 'Laravel', icon: 'tech_stack/laravel.png' },
      { name: 'MySQL', icon: 'tech_stack/mysql.png' },
    ])

    return { techStack }
  }
})
</script>

