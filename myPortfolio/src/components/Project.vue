<template>
  <section class="py-16 bg-gray-900 text-white w-full">
    <div class="max-w-6xl mx-auto px-4">
      <h2 class="text-4xl font-bold text-center mb-12">My Projects</h2>

      <div class="grid gap-8 sm:grid-cols-2 lg:grid-cols-3">
        <div
          v-for="project in projects"
          :key="project.name"
          class="bg-gray-800 rounded-4xl border overflow-hidden shadow-lg transform transition-all duration-300 hover:shadow-2xl hover:scale-105"
        >
          <img
            :src="project.image"
            :alt="project.name"
            class="w-full h-48 object-cover"
          />
          <div class="p-4">
            <h3 class="text-2xl font-semibold mb-2">{{ project.name }}</h3>
            <p class="text-gray-300 mb-4">{{ project.description }}</p>

            <!-- Tech Stack Badges -->
            <div class="flex flex-wrap gap-2 mb-4">
              <span
                v-for="tech in project.tech"
                :key="tech"
                class="px-3 py-1 bg-gray-700 rounded-full text-sm font-medium"
              >
                {{ tech }}
              </span>
            </div>

            <div class="flex p-2">
              <a
                v-if="project.github"
                :href="project.github"
                target="_blank"
                class="px-4 py-2 border border-gray-400 rounded hover:bg-gray-700 transition"
              >
                View Project
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'Projects',
  setup() {
    const projects = ref([
      {
        name: 'My Portfolio Website',
        description: 'A personal portfolio website to showcase my projects, skills, and experience.',
        image: '/project/project0.png',
        tech: ['Vue.js', 'JavaScript', 'Tailwind CSS'],
        github: 'https://github.com/lymakara-dev/portfolio-website.git'
      },
      {
        name: 'Project Management System',
        description: 'A Project Management System for tracking tasks, team collaboration, and progress monitoring.',
        image: '/project/project3.png',
        tech: ['Vue.js', 'Pinia', 'NestJS', 'MySQL'],
        github: 'https://github.com/yon-samphorslita/project-tracker.git',
      },
      {
        name: 'Articles Hosting Site',
        description: 'A blogging platform inspired by Medium, allowing users to publish, read, and engage with articles.',
        image: '/project/project2.jpg',
        tech: ['Vue.js', 'TypeScript', 'Tailwind CSS', 'Laravel', 'MySQL'],
        github: 'https://github.com/Sovanda-Mith/articles-hosting-site.git',
      },
      {
        name: 'PhoneEdge',
        description: 'PhoneEdge is an e-commerce website for high-quality phone accessories. It features a user-friendly interface and product browsing.',
        image: '/project/project1.jpg',
        tech: ['Vue.js', 'HTML', 'CSS', 'JavaScript'],
        github: 'https://github.com/lymakara-dev/vue_ecommerce.git',
      }
    ])

    return { projects }
  },
})
</script>
