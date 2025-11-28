<script setup>
import { galleryItems } from '~/store/gallery'
</script>

<template>
  <div>
    <div class="relative h-screen">
      <video
        autoplay
        loop
        muted
        class="absolute inset-0 w-full h-full object-cover"
      >
        <source src="https://alignbuilders.com/wp-content/uploads/2021/12/Hero_Video__.mp4" type="video/mp4" />
      </video>
      <div class="absolute inset-0 bg-black opacity-50"></div>
      <div
        class="relative z-10 flex flex-col items-center justify-center h-full text-center text-white"
      >
        <h1 class="text-6xl font-bold">Redefining the Construction Experience.</h1>
        <button
          class="mt-8 px-8 py-3 bg-transparent border-2 border-white text-white font-bold rounded-lg hover:bg-white hover:text-brand-dark-blue transition-colors duration-300"
        >
          Watch Video
        </button>
      </div>
    </div>

    <div class="py-24 bg-gray-100">
      <div class="container mx-auto px-6">
        <h2 class="text-4xl font-bold text-brand-dark-blue text-center">Our Work</h2>
        <div class="mt-16 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div
            v-for="item in galleryItems.slice(0, 4)"
            :key="item.slug"
            class="relative group rounded-lg overflow-hidden shadow-lg"
          >
            <img
              :src="item.src"
              alt="Project Image"
              class="w-full h-full object-cover transition-transform duration-300 transform group-hover:scale-110"
            />
            <div
              class="absolute inset-0 bg-black bg-opacity-75 flex flex-col items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity duration-300"
            >
              <h3 class="text-2xl font-bold text-white">{{ item.title }}</h3>
              <p class="text-white mt-2">{{ item.description }}</p>
              <nuxt-link
                :to="`/project/${item.slug}`"
                class="mt-4 px-4 py-2 bg-brand-maroon text-white font-bold rounded-lg"
                >Explore Project</nuxt-link
              >
            </div>
          </div>
        </div>
        <div class="text-center mt-12">
          <nuxt-link to="/gallery" class="px-8 py-3 bg-brand-maroon text-white font-bold rounded-lg hover:bg-opacity-80 transition-colors duration-300">
            Explore more projects
          </nuxt-link>
        </div>
      </div>
    </div>

    <div class="py-24 bg-brand-white">
      <div class="container mx-auto px-6 text-center">
        <h2 class="text-4xl font-bold text-brand-dark-blue">
          Delivering our clients more project clarity & greater insight.
        </h2>
        <p class="mt-4 text-xl text-gray-700 max-w-3xl mx-auto">
          We are devoted to elevating the construction experience throughout San Diego
          and Orange County. With a focus on the healthcare, science & technology, and
          higher education markets, we’re motivated by a greater purpose: to improve
          the construction environment by inspiring people to build together. From
          concept to closeout, we provide clarity, insight, and organization into
          everything we do. We call this “The Align Way.”
        </p>
      </div>
    </div>

    <div class="py-24 bg-brand-dark-blue text-white">
      <div class="container mx-auto px-6 text-center">
        <h2 class="text-4xl font-bold">Build together.</h2>
        <p class="mt-4 text-xl max-w-3xl mx-auto">
          Culture-first, people-centric approach to construction.
        </p>
        <p class="mt-8 text-lg max-w-3xl mx-auto">
          Our mission is to redefine the construction experience. With a team of
          high-character, passionate, and intentional leaders we have what it takes to
          deliver a meaningful difference. As your trusted partner we will deliver your
          project with authenticity, transparency, and purposeful human connection. It
          is this mindset that enables us to bring you a service that you can count on
          and an experience you will appreciate.
        </p>
        <div class="mt-12">
          <nuxt-link to="/about" class="px-8 py-3 bg-brand-maroon text-white font-bold rounded-lg hover:bg-opacity-80 transition-colors duration-300">
            Meet Our Leadership Team
          </nuxt-link>
        </div>
      </div>
    </div>

    <div class="py-24 bg-brand-white">
      <div class="container mx-auto px-6 text-center">
        <h2 class="text-4xl font-bold text-brand-dark-blue">Our Services</h2>
        <p class="mt-4 text-xl text-gray-700 max-w-3xl mx-auto">
          Building better, together.
        </p>
        <p class="mt-8 text-lg text-gray-700 max-w-3xl mx-auto">
          Align Builders is a leading technical builder specializing in healthcare,
          science & technology, and higher education devoted to changing the
          construction experience.
        </p>
        <div class="mt-12">
          <a href="#" class="px-8 py-3 bg-brand-maroon text-white font-bold rounded-lg hover:bg-opacity-80 transition-colors duration-300">
            Read More About Our Services
          </a>
        </div>
      </div>
    </div>

    <div class="py-24 bg-gray-100">
      <div class="container mx-auto px-6">
        <h2 class="text-4xl font-bold text-brand-dark-blue text-center">News</h2>
        <div class="mt-16 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div class="bg-white rounded-lg shadow-lg overflow-hidden">
            <img
              src="https://alignbuilders.com/wp-content/uploads/2023/01/IMG_3522-300x300.jpg"
              alt="News Image"
              class="w-full h-64 object-cover"
            />
            <div class="p-6">
              <p class="text-gray-600">Jan 26, 2023</p>
              <h3 class="mt-2 text-2xl font-bold text-brand-dark-blue">
                Team Building: Day of Service
              </h3>
              <p class="mt-2 text-gray-700">
                Last weekends (1/21/23) the Align Team had the privilege of working with
                Alabaster Jar, a nonprofit empowering survivors of human trafficking...
              </p>
            </div>
          </div>
          <div class="bg-white rounded-lg shadow-lg overflow-hidden">
            <img
              src="https://alignbuilders.com/wp-content/uploads/2021/12/Untitleddesign8-300x300.jpg"
              alt="News Image"
              class="w-full h-64 object-cover"
            />
            <div class="p-6">
              <p class="text-gray-600">Oct 06, 2021</p>
              <h3 class="mt-2 text-2xl font-bold text-brand-dark-blue">
                An Exciting Project Win for Align Builders and the Environment
              </h3>
              <p class="mt-2 text-gray-700">
                PROJECT | SOARS Instrument Make-Ready Lab Phase 1  TYPE | LIFE SCIENCE LAB The
                newly built Scripps Institution of Oceanography…
              </p>
            </div>
          </div>
          <div class="bg-white rounded-lg shadow-lg overflow-hidden">
            <img
              src="https://alignbuilders.com/wp-content/uploads/2021/09/align-builders-bim-investment-300x300.jpg"
              alt="News Image"
              class="w-full h-64 object-cover"
            />
            <div class="p-6">
              <p class="text-gray-600">Mar 28, 2019</p>
              <h3 class="mt-2 text-2xl font-bold text-brand-dark-blue">
                Finding the Return on Your Small-Project BIM Investment
              </h3>
              <p class="mt-2 text-gray-700">
                Building Information Modeling (BIM) is too often associated with large,
                ground-up projects where prefabrication and trade coordination can
                happen well…
              </p>
            </div>
          </div>
        </div>
        <div class="text-center mt-12">
          <a href="#" class="px-8 py-3 bg-brand-maroon text-white font-bold rounded-lg hover:bg-opacity-80 transition-colors duration-300">
            See All News
          </a>
        </div>
      </div>
    </div>
  </div>
</template>
