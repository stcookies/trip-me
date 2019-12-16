<template>
  <div id="app" class="antialiased">
    <Navbar/>
    <section class="bg-bottom bg-cover py-56" style="background-image: url('https://images.unsplash.com/photo-1463693396721-8ca0cfa2b3b5?ixlib=rb-1.2.1&auto=format&fit=crop&w=2550&q=80')">
      <div class="flex flex-col items-center">
        <span class="text-5xl sm:text-6xl px-4 text-white text-center font-semibold">The Perfect Trip Made Easy</span>
        <span class="text-3xl px-4 text-white text-center leading-none">Let us plan your next getaway</span>
        <form class="mt-8 w-11/12 sm:w-3/4 md:w-auto md:flex bg-white rounded-lg shadow-2xl">
          <div class="py-6 md:py-4 md:w-48 lg:w-64 border-b md:border-b-0 md:border-r">
            <label class="px-4 text-gray-500" for="from">From</label>
            <Dropdown prompt="Departing Location" :options="departures"/>
          </div>
          <div class="py-6 md:py-4 md:w-48 lg:w-64 border-b md:border-b-0 md:border-r">
            <label class="px-4 text-gray-500" for="to">To</label>
            <Dropdown prompt="Destination" :options="arrivals"/>
          </div>
          <div class="py-6 md:py-4 md:w-48 lg:w-64">
            <label class="px-4 text-gray-500" for="from">When</label>
            <img src="./assets/img/calendar.svg" class="ml-4 h-8 w-8"/>
          </div>
          <a href="#" class="py-5 px-6 md:px-10 flex items-center justify-center focus:outline-none focus:shadow-outline inline-block rounded-b-lg md:rounded-b-none md:rounded-r-lg bg-red-500 text-white text-xl">Search</a>
        </form>
      </div>
    </section>
    <section class="flex justify-center bg-gray-200 px-4 pt-8">
      <!--div class="w-1/2 max-w-xl">
        <h1 class="text-2xl font-semibold">Filters</h1>
      </div-->
      <div class="w-full xl:max-w-6xl">
        <span class="text-2xl font-semibold">Trending Now</span>
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
