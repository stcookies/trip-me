<template>
  <div>
    <div class="hidden p-4 bg-white rounded shadow md:flex">
      <div class="flex flex-wrap w-1/2 lg:w-2/3">
        <img class="object-cover w-full h-64 max-w-2xl pr-4 xl:w-1/2 xl:pr-0" :src="destination.image" :alt="destination.location">
        <div class="pl-6">
          <span class="block pt-5 text-2xl font-semibold tracking-wide uppercase lg:pt-0">{{ destination.location }}</span>
          <span class="block text-sm text-gray-500">{{ destination.country }}</span>
          <div class="flex pt-2">
            <svg v-for="i in 5" :key="i" viewBox="0 0 24 24" :class="i <= destination.rating ? 'text-yellow-400' : 'text-gray-400'" class="w-4 h-4 fill-current">
              <path d="M8.128 19.825a1.586 1.586 0 0 1-1.643-.117 1.543 1.543 0 0 1-.53-.662 1.515 1.515 0 0 1-.096-.837l.736-4.247-3.13-3a1.514 1.514 0 0 1-.39-1.569c.09-.271.254-.513.475-.698.22-.185.49-.306.776-.35L8.66 7.73l1.925-3.862c.128-.26.328-.48.577-.633a1.584 1.584 0 0 1 1.662 0c.25.153.45.373.577.633l1.925 3.847 4.334.615c.29.042.562.162.785.348.224.186.39.43.48.704a1.514 1.514 0 0 1-.404 1.58l-3.13 3 .736 4.247c.047.282.014.572-.096.837-.111.265-.294.494-.53.662a1.582 1.582 0 0 1-1.643.117l-3.865-2-3.865 2z" />
            </svg>
          </div>
          <span class="inline-block pb-3 text-xs font-semibold text-blue-500">From {{ destination.reviews }} reviews</span>
          <div class="flex justify-between pt-3 border-t border-gray-300">
            <div class="pr-20">
              <span class="font-medium">Duration</span>
              <span class="block pb-3 text-sm text-gray-500 font">{{ destination.duration }}</span>
              <span class="font-medium">Flight Type</span>
              <span class="block text-sm text-gray-500">{{ destination.flightType }}</span>
            </div>
            <div>
              <span class="font-medium">Activities</span>
              <span class="block pb-3 text-sm text-gray-500">{{ destination.activities }}</span>
              <span class="font-medium">Hotel</span>
              <span class="block text-sm text-gray-500">{{ destination.hotel }}</span>
            </div>
          </div>
          <a href="#" class="inline-block mt-2 text-xs text-blue-500 opacity-75">View full itinerary &#8594;</a>
        </div>
      </div>
      <div class="flex flex-col items-center justify-center w-1/2 mt-5 lg:w-1/3 md:mt-0 md:border-l md:border-gray-300">
        <span class="block px-4 py-1 mb-3 ml-6 text-sm font-bold tracking-wide text-white uppercase bg-green-300">25% Off</span>
        <span class="text-5xl font-semibold leading-none">${{ destination.price }}</span>
        <span class="block mt-1 text-sm leading-none text-center text-gray-500">per person</span>
        <a href="#" class="px-12 py-4 mt-6 font-semibold text-white bg-red-500 rounded-lg xl:px-20 focus:outline-none focus:shadow-outline">Book&#160;Now</a>
      </div>
    </div>
    <div class="flex flex-col items-center mb-10 md:hidden">
      <img class="object-cover rounded-lg shadow-md" :src="destination.image" :alt="destination.location">
      <div class="w-11/12 -mt-12 md:w-4/5">
        <div class="flex flex-wrap p-6 bg-white rounded-lg shadow-lg"> <!-- entire card -->
          <div class="flex flex-col items-center w-full pr-3 text-center sm:w-1/2">
            <span class="block text-3xl font-semibold tracking-wide uppercase">{{ destination.location }}</span>
            <span class="block leading-none text-gray-500 sm:pt-0 text-md">{{ destination.country }}</span>
            <div class="flex pt-3">
              <svg v-for="i in 5" :key="i" viewBox="0 0 24 24" :class="i <= destination.rating ? 'text-yellow-400' : 'text-gray-400'" class="w-6 h-6 fill-current">
                <path d="M8.128 19.825a1.586 1.586 0 0 1-1.643-.117 1.543 1.543 0 0 1-.53-.662 1.515 1.515 0 0 1-.096-.837l.736-4.247-3.13-3a1.514 1.514 0 0 1-.39-1.569c.09-.271.254-.513.475-.698.22-.185.49-.306.776-.35L8.66 7.73l1.925-3.862c.128-.26.328-.48.577-.633a1.584 1.584 0 0 1 1.662 0c.25.153.45.373.577.633l1.925 3.847 4.334.615c.29.042.562.162.785.348.224.186.39.43.48.704a1.514 1.514 0 0 1-.404 1.58l-3.13 3 .736 4.247c.047.282.014.572-.096.837-.111.265-.294.494-.53.662a1.582 1.582 0 0 1-1.643.117l-3.865-2-3.865 2z" />
              </svg>
            </div>
            <span class="inline-block pb-3 font-semibold text-blue-500 text-md">From {{ destination.reviews }} reviews</span>
          </div>
          <div class="flex flex-wrap items-center justify-center w-full pt-3 text-center sm:w-1/2 sm:pl-10 sm:pt-0 sm:border-l sm:border-gray-300">
            <div class="w-1/2">
              <span class="font-medium">Duration</span>
              <span class="block pb-3 text-sm text-gray-500 font">{{ destination.duration }}</span>
              <span class="block pt-3 font-medium">Flight Type</span>
              <span class="block text-sm text-gray-500">{{ destination.flightType }}</span>
            </div>
            <div class="w-1/2">
              <span class="font-medium">Activities</span>
              <span class="block pb-3 text-sm text-gray-500">{{ destination.activities }}</span>
              <span class="block pt-3 font-medium">Hotel</span>
              <span class="block text-sm text-gray-500">{{ destination.hotel }}</span>
            </div>
            <div class="w-full pt-4">
              <a href="#" class="inline-block mt-2 text-xs text-blue-500 opacity-75">View full itinerary &#8594;</a>
            </div>
          </div>
          <div class="flex flex-wrap justify-around w-full mt-8 text-center border-t border-gray-300">
            <div class="flex flex-col pt-5 mx-3">
              <span class="block px-2 py-1 mb-3 text-sm font-bold tracking-wide text-white uppercase bg-green-300">25% Off</span>
              <span class="text-4xl font-semibold leading-none">${{ destination.price }}</span>
              <span class="block mt-1 text-sm leading-none text-center text-gray-500">per person</span>
            </div>
            <a href="#" class="self-center px-8 py-3 mx-3 mt-5 font-semibold text-white bg-red-500 rounded-lg sm:mt-0 focus:outline-none focus:shadow-outline">Book&#160;Now</a>
          </div>
        </div>
      </div>
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