<template>
  <div class="min-h-screen bg-gradient-to-b from-gray-900 via-gray-800 to-gray-900">
    <NavBar />
    <section id="hero" class="animate-section opacity-0 translate-y-8 min-h-screen flex items-center justify-center snap-start">
      <Hero />
    </section>
    <section class="animate-section opacity-0 translate-y-8">
      <TechStack />
    </section>
    <section id="projects" class="animate-section opacity-0 translate-y-8 min-h-screen w-full flex items-center justify-center snap-start">
      <Projects />
    </section>
    <section id="volunteer" class="animate-section opacity-0 translate-y-8 min-h-screen flex items-center justify-center snap-start">
      <Volunteer />
    </section>
    <section id="contact" class="animate-section opacity-0 translate-y-8">
      <ContactMe />
    </section>
  </div>

  
</template>

<script lang="ts">
import NavBar from './components/navbar.vue'
import HelloWorld from './components/HelloWorld.vue'
import Hero from './components/Hero.vue'
import TechStack from './components/TechStack.vue'
import Projects from './components/Project.vue'
import Volunteer from './components/volunteer_experience.vue'
import ContactMe from './components/Contact.vue'
import { ref } from 'vue'
import { onMounted } from 'vue'

export default {
  components: {
    NavBar,
    HelloWorld,
    Hero,
    TechStack,
    Projects,
    Volunteer,
    ContactMe
  },
  setup() {
    const sections = ref<HTMLElement[]>([])

    onMounted(() => {
      sections.value = Array.from(document.querySelectorAll('.animate-section')) as HTMLElement[]

      const observer = new IntersectionObserver(
        (entries) => {
          entries.forEach(entry => {
            if (entry.isIntersecting) {
              entry.target.classList.remove('opacity-0', 'translate-y-8')
              entry.target.classList.add('opacity-100', 'translate-y-0')
            } else {
              // Optional: reverse animation when scrolling back up
              entry.target.classList.add('opacity-0', 'translate-y-8')
              entry.target.classList.remove('opacity-100', 'translate-y-0')
            }
          })
        },
        { threshold: 0.2 } // triggers when 20% visible
      )

      sections.value.forEach(sec => observer.observe(sec))
    })
  }
}
</script>

<style>
.opacity-0 { opacity: 0; }
.opacity-100 { opacity: 1; transition: all 0.5s ease-out; }
.translate-y-8 { transform: translateY(5rem); }
.translate-y-0 { transform: translateY(0); transition: all 0.5s ease-out; }
</style>