<template>
  <div class="p-4 flex flex-wrap bg-white shadow rounded">
    <div class="w-full lg:w-2/3 flex flex-wrap">
      <img class="h-64 w-64 object-cover" :src="destination.image">
      <div class="pl-6">
        <span class="block uppercase tracking-wide font-semibold text-2xl">{{ destination.location }}</span>
        <span class="block text-sm text-gray-500">{{ destination.country }}</span>
        <div class="pt-2 flex">
          <svg v-for="i in 5" :key="i" viewBox="0 0 24 24" :class="i <= destination.rating ? 'text-yellow-400' : 'text-gray-400'" class="h-4 w-4 fill-current">
            <path d="M8.128 19.825a1.586 1.586 0 0 1-1.643-.117 1.543 1.543 0 0 1-.53-.662 1.515 1.515 0 0 1-.096-.837l.736-4.247-3.13-3a1.514 1.514 0 0 1-.39-1.569c.09-.271.254-.513.475-.698.22-.185.49-.306.776-.35L8.66 7.73l1.925-3.862c.128-.26.328-.48.577-.633a1.584 1.584 0 0 1 1.662 0c.25.153.45.373.577.633l1.925 3.847 4.334.615c.29.042.562.162.785.348.224.186.39.43.48.704a1.514 1.514 0 0 1-.404 1.58l-3.13 3 .736 4.247c.047.282.014.572-.096.837-.111.265-.294.494-.53.662a1.582 1.582 0 0 1-1.643.117l-3.865-2-3.865 2z" />
          </svg>
        </div>
        <span class="inline-block pb-4 text-xs font-semibold text-blue-500">From {{ destination.reviews }} reviews</span>
        <div class="pt-4 border-t border-gray-300">
          <div class="flex">
            <div class="pr-20">
              <span class="font-medium">Duration</span>
              <span class="block pb-5 font text-sm text-gray-500">{{ destination.duration }}</span>
              <span class="font-medium">Flight Type</span>
              <span class="block text-sm text-gray-500">{{ destination.flightType }}</span>
            </div>
            <div>
              <span class="font-medium">Activities</span>
              <span class="block pb-5 text-sm text-gray-500">{{ destination.activities }}</span>
              <span class="font-medium">Hotel</span>
              <span class="block text-sm text-gray-500">{{ destination.hotel }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="w-full md:w-1/3 mt-5 lg:mt-0 flex flex-wrap flex-col justify-center items-center lg:border-l lg:border-gray-300">
      <span class="ml-6 mb-3 block text-sm text-white bg-green-300 font-bold px-4 py-1 uppercase tracking-wide">25% Off</span>
      <span class="font-semibold leading-none text-5xl">${{ destination.price }}</span>
      <span class="block text-center leading-none mt-1 text-sm text-gray-500">per person</span>
      <a href="#" class="mt-6 px-20 py-4 bg-red-500 text-white font-semibold rounded-lg">Book Now</a>
    </div>
  </div>
</template>

<script>
export default {
  props: ['destination'],
  data() {
    return {

    }
  }
}
</script>

<style>
</style>