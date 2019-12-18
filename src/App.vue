<template>
  <div id="app" class="antialiased">
    <Navbar/>
    <section class="py-56 bg-bottom bg-cover" style="background-image: url('https://images.unsplash.com/photo-1463693396721-8ca0cfa2b3b5?ixlib=rb-1.2.1&auto=format&fit=crop&w=2550&q=80')">
      <div class="flex flex-col items-center">
        <span class="px-4 text-5xl font-semibold text-center text-white sm:text-6xl">The Perfect Trip Made Easy</span>
        <span class="px-4 text-3xl leading-none text-center text-white">Let us plan your next getaway</span>
        <form class="w-11/12 mt-8 bg-white rounded-lg shadow-2xl sm:w-3/4 md:w-auto md:flex">
          <div class="py-6 border-b md:py-4 md:w-48 lg:w-64 md:border-b-0 md:border-r">
            <label class="px-4 text-gray-500" for="from">From</label>
            <Dropdown prompt="Departing Location" :options="departures"/>
          </div>
          <div class="py-6 border-b md:py-4 md:w-48 lg:w-64 md:border-b-0 md:border-r">
            <label class="px-4 text-gray-500" for="to">To</label>
            <Dropdown prompt="Destination" :options="arrivals"/>
          </div>
          <div class="py-6 md:py-4 md:w-48 lg:w-64">
            <label class="px-4 text-gray-500" for="from">When</label>
            <img src="./assets/img/calendar.svg" class="w-8 h-8 ml-4"/>
          </div>
          <a href="#" class="flex items-center justify-center inline-block px-6 py-5 text-xl text-white bg-red-500 rounded-b-lg md:px-10 focus:outline-none focus:shadow-outline md:rounded-b-none md:rounded-r-lg">Search</a>
        </form>
      </div>
    </section>
    <section class="flex flex-wrap px-4 pt-8 -mx-2 bg-gray-200 lg:justify-center">
      <div class="w-full px-2 lg:hidden">
        <a class="text-xl text-blue-500 cursor-pointer" @click="showFilters = !showFilters">{{ showFilters ? 'Hide Filters' : 'Filter Destinations &#8250;' }}</a>
      </div>
      <div class="self-start w-full max-w-sm px-2 lg:block lg:w-1/3 lg:mt-0" :class="showFilters ? 'block' : 'hidden'">
        <h1 class="hidden text-2xl font-semibold lg:block">Filters</h1>
        <div class="flex flex-col flex-wrap p-8 mt-4 bg-white rounded-lg shadow">
          <span class="text-lg font-semibold text-gray-800">Categories</span>
          <div class="flex flex-wrap items-center justify-between pt-3">
            <div class="w-full sm:w-1/2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="text-md">Honeymoon</span>
            </div>
            <div class="w-full pt-2 sm:pt-0 sm:w-1/2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="text-md">Family</span>
            </div>
            <div class="w-full pt-2 sm:w-1/2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="text-md">Friends</span>
            </div>
          </div>
          <span class="block pt-8 text-lg font-semibold text-gray-800">Days</span>
          <div class="flex flex-wrap items-center justify-between pt-3">
            <div class="w-full sm:w-1/2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="text-md">1-2</span>
            </div>
            <div class="w-full pt-2 sm:pt-0 sm:w-1/2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="text-md">3-5</span>
            </div>
            <div class="w-full pt-2 sm:w-1/2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="text-md">6-8</span>
            </div>
            <div class="w-full pt-2 sm:w-1/2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="text-md">8-10</span>
            </div>
            <div class="w-full pt-2 sm:w-1/2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="text-md">11+</span>
            </div>
          </div>
          <span class="block pt-8 text-lg font-semibold text-gray-800">Budget (USD)</span>
          <div class="flex flex-wrap pt-3">
            <div class="w-full sm:w-1/2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="text-md">0-1000</span>
            </div>
            <div class="w-full pt-2 sm:pt-0 sm:w-1/2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="text-md">1000-2500</span>
            </div>
            <div class="w-full pt-2 sm:w-1/2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="text-md">2500-5000</span>
            </div>
            <div class="w-full pt-2 sm:w-1/2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="text-md">5000-7500</span>
            </div>
            <div class="w-full pt-2 sm:w-1/2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="text-md">7500-10,000</span>
            </div>
            <div class="w-full pt-2 sm:w-1/2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="text-md">10,000+</span>
            </div>
          </div>
          <span class="block pt-8 text-lg font-semibold text-gray-800">Hotel Rating</span>
          <div class="pt-3">
            <div class="flex items-center">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="pr-2 text-md">5 star</span>
              <svg v-for="i in 5" :key="i" viewBox="0 0 24 24" :class="i <= 5 ? 'text-yellow-400' : 'text-gray-400'" class="w-4 h-4 fill-current">
                <path d="M8.128 19.825a1.586 1.586 0 0 1-1.643-.117 1.543 1.543 0 0 1-.53-.662 1.515 1.515 0 0 1-.096-.837l.736-4.247-3.13-3a1.514 1.514 0 0 1-.39-1.569c.09-.271.254-.513.475-.698.22-.185.49-.306.776-.35L8.66 7.73l1.925-3.862c.128-.26.328-.48.577-.633a1.584 1.584 0 0 1 1.662 0c.25.153.45.373.577.633l1.925 3.847 4.334.615c.29.042.562.162.785.348.224.186.39.43.48.704a1.514 1.514 0 0 1-.404 1.58l-3.13 3 .736 4.247c.047.282.014.572-.096.837-.111.265-.294.494-.53.662a1.582 1.582 0 0 1-1.643.117l-3.865-2-3.865 2z" />
              </svg>
            </div>
            <div class="flex items-center pt-2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="pr-2 text-md">4 star</span>
              <svg v-for="i in 5" :key="i" viewBox="0 0 24 24" :class="i <= 4 ? 'text-yellow-400' : 'text-gray-400'" class="w-4 h-4 fill-current">
                <path d="M8.128 19.825a1.586 1.586 0 0 1-1.643-.117 1.543 1.543 0 0 1-.53-.662 1.515 1.515 0 0 1-.096-.837l.736-4.247-3.13-3a1.514 1.514 0 0 1-.39-1.569c.09-.271.254-.513.475-.698.22-.185.49-.306.776-.35L8.66 7.73l1.925-3.862c.128-.26.328-.48.577-.633a1.584 1.584 0 0 1 1.662 0c.25.153.45.373.577.633l1.925 3.847 4.334.615c.29.042.562.162.785.348.224.186.39.43.48.704a1.514 1.514 0 0 1-.404 1.58l-3.13 3 .736 4.247c.047.282.014.572-.096.837-.111.265-.294.494-.53.662a1.582 1.582 0 0 1-1.643.117l-3.865-2-3.865 2z" />
              </svg>
            </div>
            <div class="flex items-center pt-2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="pr-2 text-md">3 star</span>
              <svg v-for="i in 5" :key="i" viewBox="0 0 24 24" :class="i <= 3 ? 'text-yellow-400' : 'text-gray-400'" class="w-4 h-4 fill-current">
                <path d="M8.128 19.825a1.586 1.586 0 0 1-1.643-.117 1.543 1.543 0 0 1-.53-.662 1.515 1.515 0 0 1-.096-.837l.736-4.247-3.13-3a1.514 1.514 0 0 1-.39-1.569c.09-.271.254-.513.475-.698.22-.185.49-.306.776-.35L8.66 7.73l1.925-3.862c.128-.26.328-.48.577-.633a1.584 1.584 0 0 1 1.662 0c.25.153.45.373.577.633l1.925 3.847 4.334.615c.29.042.562.162.785.348.224.186.39.43.48.704a1.514 1.514 0 0 1-.404 1.58l-3.13 3 .736 4.247c.047.282.014.572-.096.837-.111.265-.294.494-.53.662a1.582 1.582 0 0 1-1.643.117l-3.865-2-3.865 2z" />
              </svg>
            </div>
            <div class="flex items-center pt-2">
              <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
              <span class="pr-2 text-md">2 star</span>
              <svg v-for="i in 5" :key="i" viewBox="0 0 24 24" :class="i <= 2 ? 'text-yellow-400' : 'text-gray-400'" class="w-4 h-4 fill-current">
                <path d="M8.128 19.825a1.586 1.586 0 0 1-1.643-.117 1.543 1.543 0 0 1-.53-.662 1.515 1.515 0 0 1-.096-.837l.736-4.247-3.13-3a1.514 1.514 0 0 1-.39-1.569c.09-.271.254-.513.475-.698.22-.185.49-.306.776-.35L8.66 7.73l1.925-3.862c.128-.26.328-.48.577-.633a1.584 1.584 0 0 1 1.662 0c.25.153.45.373.577.633l1.925 3.847 4.334.615c.29.042.562.162.785.348.224.186.39.43.48.704a1.514 1.514 0 0 1-.404 1.58l-3.13 3 .736 4.247c.047.282.014.572-.096.837-.111.265-.294.494-.53.662a1.582 1.582 0 0 1-1.643.117l-3.865-2-3.865 2z" />
              </svg>
            </div>
          </div>
        </div>
      </div>
      <div class="self-center w-full max-w-6xl px-2 mt-5 lg:w-2/3 lg:mt-0">
        <span class="text-2xl font-semibold">Popular Destinations</span>
        <div class="mt-4" v-for="(destination, index) in destinations" :key="index">
          <DestinationCard :destination="destination"/>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Navbar from './components/Navbar'
import Dropdown from './components/Dropdown'
import DestinationCard from './components/DestinationCard'
export default {
  name: 'app',
  components: {
    Navbar,
    Dropdown,
    DestinationCard
  },
  data() {
    return {
      showFilters: false,
      departures: ['Los Angeles, CA', 'Dallas, TX', 'Chicago, IL', 'Cincinnati, OH', 'Seattle, WA'],
      arrivals: ['Tokyo, JP', 'London, UK', 'Cape Town, SA', 'Melbourne, AU', 'Phuket, TH'],
      destinations: [
        { location: 'Phuket', country: 'Thailand', rating: 5, reviews: 275, duration: '6 Nights, 7 Days', hotel: '5 Star Hotel', activities: 33, flightType: 'Coach', price: 875, image: 'https://images.unsplash.com/photo-1551418843-01c6b62e864d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80' },
        { location: 'Los Angeles, CA', country: 'United States', rating: 3, reviews: 85, duration: '4 Nights, 5 Days', hotel: '3 Star Hotel', activities: 16, flightType: 'Coach', price: 650, image: 'https://images.unsplash.com/photo-1429554429301-1c7d5ae2d42e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80' },
        { location: 'Tokyo', country: 'Japan', rating: 5, reviews: 126, duration: '6 Nights, 5 Days', hotel: '5 Star Hotel', activities: 38, flightType: 'First Class', price: 1375, image: 'https://images.unsplash.com/photo-1558632328-465f59aff245?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80' },
        { location: 'Chicago, IL', country: 'United States', rating: 3, reviews: 112, duration: '3 Nights, 4 Days', hotel: '3 Star Hotel', activities: 19, flightType: 'Economy', price: 565, image: 'https://images.unsplash.com/photo-1494522358652-f30e61a60313?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80' },
        { location: 'London', country: 'United Kingdom', rating: 4, reviews: 67, duration: '6 Nights, 7 Days', hotel: '4 Star Hotel', activities: 25, flightType: 'Economy Plus', price: 1250, image: 'https://images.unsplash.com/photo-1505761671935-60b3a7427bad?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80' },
        { location: 'Cape Town', country: 'South Africa', rating: 3, reviews: 113, duration: '3 Nights, 4 Days', hotel: '3 Star Hotel', activities: 22, flightType: 'First Class', price: 1525, image: 'https://images.unsplash.com/photo-1543261534-09e5f83a86c2?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80' },
        { location: 'Melbourne', country: 'Australia', rating: 4, reviews: 176, duration: '4 Nights, 5 Days', hotel: '4 Star Hotel', activities: 27, flightType: 'Economy', price: 1025, image: 'https://images.unsplash.com/photo-1545044846-351ba102b6d5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80' },
      ]
    }
  }
}
</script>

<style src="./css/tailwind.css"/>
