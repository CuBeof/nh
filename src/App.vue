<template>
  <section class="min-w-full min-h-screen">
    <div class="bg-gray-900 fixed inset-0 -z-10"></div>
    <main class="my-20 p-4 md:p-7 lg:p-10">
      <div
      class="container mx-auto text-white max-w-6xl p-4 md:p-7 lg:p-10  rounded-2xl overflow-auto">
      <!-- Search bar -->
        <h1
          class="mb-6 text-4xl font-extrabold leading-none tracking-tight text-center md:text-5xl lg:text-6xl text-gray-100">
          <span class="text-transparent bg-clip-text bg-gradient-to-r to-emerald-600 from-sky-400">
            Import Product
          </span>
        </h1>
        <form class="my-6 flex flex-col items-center">
          <div class="flex w-full space-x-2">
            <input
              v-model="url"
              type="text"
              class="flex flex-shink bg-black bg-opacity-30 w-full p-2.5 border border-violet-500 rounded-md text-gray-100 placeholder-gray-500 focus:placeholder-gray-300 focus:ring focus:ring-violet-400 focus:border-violet-400 focus:outline-none"
              placeholder="Paste product url here">
            <button
              @click="importProduct"
              class="inline-flex items-center justify-center px-5 py-3 text-base font-medium text-center text-white bg-violet-700 rounded-lg hover:bg-violet-800 hover:ring focus:ring ring-violet-400">
              Import
            </button>
          </div>
        </form>
        <!-- List product -->
        <div class="h-screen">
      </div>
      </div>
    </main>
  </section>
</template>

<script setup>
  import { ref } from 'vue'
  import axios from "axios"
  import { IMPORT_PRODUCT_ENPOINT } from './constant'

  const url = ref()
  async function importProduct(event) {
    event.preventDefault()

    try {
      const response = await axios.post(
      IMPORT_PRODUCT_ENPOINT,
        url.value
      )
    }
    catch (error) {
      console.log(error.message)

    }
  }
</script>
