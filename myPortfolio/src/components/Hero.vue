<template>
  <section class="min-h-screen w-full flex items-center justify-center text-white px-6">
    <div
      class=" w-full flex flex-col-reverse md:flex-row items-center justify-around"
    >
      <!-- Text Content -->
      <div class="text-center md:text-left max-w-xl space-y-6">
        <h1 class="text-4xl md:text-5xl font-bold">
          Kong Sopheakvortey
        </h1>

        <h2 class="text-xl md:text-2xl text-gray-300 font-medium">
          Web Developer
        </h2>

        <p class="text-gray-400 leading-relaxed">
            I am an aspiring full-stack web developer who enjoys building clean, 
            modern, and user-friendly web applications and is actively exploring 
            back-end technologies. Explore my projects and feel free to reach out.
        </p>

        <!-- CTA Buttons (optional but recommended) -->
        <div class="flex justify-center md:justify-start gap-4 pt-4">
          <a
            href="KONG_Sopheakvortey_resume.pdf"
            download
            class="px-6 py-2 bg-white text-gray-900 rounded-lg font-medium hover:bg-gray-200 transition"
          >
            Download Resume
          </a>

          <a
            href="#contact"
            class="px-6 py-2 border border-gray-400 rounded-lg hover:bg-gray-700 transition"
          >
            Contact Me
          </a>
        </div>
      </div>

      <!-- Image -->
      <div class="flex justify-center w-full md:w-auto">
        <div class="rounded-full p-2 bg-gray-800 shadow-xl">
          <img
            src="../assets/pf.jpg"
            alt="Kong Sopheakvortey"
            class="w-56 h-56 md:w-[500px] md:h-[700px] rounded-full object-cover"
          />
        </div>
      </div>
    </div>
  </section>
</template>
