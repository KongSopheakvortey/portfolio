<template>
  <section class="py-16 bg-gray-900 text-white w-full">
    <div class="max-w-6xl mx-auto px-4">
      <h2 class="text-4xl font-bold text-center mb-12">
        Volunteer Experience
      </h2>

      <div class="space-y-8">
        <div
          v-for="item in volunteerExperiences"
          :key="item.role"
          class="bg-gray-800 border rounded-xl p-6 hover:shadow-lg transition"
        >
          <div class="flex flex-col md:flex-row md:justify-between md:items-center mb-3">
            <h3 class="text-2xl font-semibold">
              {{ item.role }}
            </h3>
            <span class="text-gray-400 text-sm">
              {{ item.duration }}
            </span>
          </div>

          <p class="text-gray-300 font-medium">
            {{ item.organization }}
          </p>

          <p class="text-gray-400 mt-3">
            {{ item.description }}
          </p>

          <!-- Skills / Tech used -->
          <div class="flex flex-wrap gap-2 mt-4">
            <span
              v-for="skill in item.skills"
              :key="skill"
              class="px-3 py-1 bg-gray-700 rounded-full text-sm"
            >
              {{ skill }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'VolunteerExperience',
  setup() {
    const volunteerExperiences = ref([
      {
        role: 'Member of Speaker Curation Team',
        organization: 'Tedx',
        duration: 'June 2025 - Oct 2025',
        description:
            'Responsible for contacting and coordinating speakers during the pre-event phase, and supporting the People Experience Team with attendee registration on the event day.',
        skills: ['Communication', 'Organization', 'Teamwork', 'Coordination', 'Attendee Management'],
      },
      {
        role: 'Member of Speaker Coordinator team',
        organization: 'Joblink career and internship fair',
        duration: 'Sept 2024 - Mar 2025',
        description:
          'Responsible for contacting the speaker that is well suited to the theme of the workshop during the pre-event day.',
        skills: ['Communication', 'Organization', 'Coordination', 'Teamwork'],
      },
      {
        role: 'Member of Technical team',
        organization: 'National Teaching Conference',
        duration: 'August 2024',
        description:
          'Responsible for checking the projectors and laptops for the break room workshop. Assisting speakers with technical issues during their presentations.',
        skills: ['Technical Support', 'Event Setup', 'Problem Solving', 'Teamwork'],
      },
    ])

    return { volunteerExperiences }
  },
})
</script>
