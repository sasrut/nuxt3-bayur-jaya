<template>
  <div class="py-24">
    <div class="container mx-auto px-6">
      <h1 class="text-5xl font-bold text-brand-dark-blue text-center">Contact Us</h1>
      <p class="mt-4 text-xl text-gray-700 text-center max-w-3xl mx-auto">
        We'd love to hear from you. Reach out to us for any inquiries.
      </p>

      <div class="mt-16 max-w-4xl mx-auto">
        <form class="bg-white p-8 rounded-lg shadow-lg">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div class="mb-4">
              <label for="name" class="block text-gray-700 font-bold mb-2">Name</label>
              <input type="text" id="name" class="w-full px-4 py-3 border rounded-lg" />
            </div>
            <div class="mb-4">
              <label for="email" class="block text-gray-700 font-bold mb-2">Email</label>
              <input type="email" id="email" class="w-full px-4 py-3 border rounded-lg" />
            </div>
          </div>
          <div class="mb-4">
            <label for="subject" class="block text-gray-700 font-bold mb-2">Subject</label>
            <input type="text" id="subject" class="w-full px-4 py-3 border rounded-lg" />
          </div>
          <div class="mb-4">
            <label for="message" class="block text-gray-700 font-bold mb-2">Message</label>
            <textarea id="message" rows="6" class="w-full px-4 py-3 border rounded-lg"></textarea>
          </div>
          <button
            type="submit"
            class="w-full bg-brand-maroon text-white font-bold py-3 px-4 rounded-lg hover:bg-opacity-80 transition-colors duration-300"
          >
            Send Message
          </button>
        </form>

        <div class="mt-16 text-center text-gray-700">
          <h2 class="text-3xl font-bold text-brand-dark-blue">Our Office</h2>
          <div class="mt-8 flex flex-col md:flex-row items-center justify-center space-y-4 md:space-y-0 md:space-x-8">
            <div class="flex items-center">
              <svg class="w-8 h-8 mr-2 fill-current text-brand-dark-blue" viewBox="0 0 24 24">
                <path
                  d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"
                />
              </svg>
              <p class="text-lg">10620 Treena Street, Suite 230, San Diego, CA 92131</p>
            </div>
            <div class="flex items-center">
              <svg class="w-8 h-8 mr-2 fill-current text-brand-dark-blue" viewBox="0 0 24 24">
                <path
                  d="M6.62 10.79a15.55 15.55 0 0 0 6.59 6.59l2.2-2.2c.27-.27.67-.36 1.02-.24 1.12.37 2.33.57 3.57.57.55 0 1 .45 1 1v3.5c0 .55-.45 1-1 1C10.12 22 2 13.88 2 4c0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.24.2 2.45.57 3.57.11.35.03.74-.25 1.02l-2.2 2.2z"
                />
              </svg>
              <p class="text-lg">(858) 433-2500</p>
            </div>
            <div class="flex items-center">
              <svg class="w-8 h-8 mr-2 fill-current text-brand-dark-blue" viewBox="0 0 24 24">
                <path
                  d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"
                />
              </svg>
              <p class="text-lg">info@alignbuilders.com</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
