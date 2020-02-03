<template>
  <div id="app" class="antialiased text-gray-800">
    <Navbar />
    <section
      class="py-56 bg-bottom bg-cover"
      style="background-image: url('https://images.unsplash.com/photo-1463693396721-8ca0cfa2b3b5?ixlib=rb-1.2.1&auto=format&fit=crop&w=2550&q=100')"
    >
      <div class="flex flex-col items-center">
        <span
          class="px-4 text-5xl font-semibold text-center text-white sm:text-6xl"
        >The Perfect Trip Made Easy</span>
        <span
          class="px-4 text-3xl leading-none text-center text-white"
        >Let us plan your next getaway</span>
        <form class="w-11/12 mt-8 bg-white rounded-lg shadow-2xl sm:w-3/4 md:w-auto md:flex">
          <div class="py-6 border-b md:py-4 md:w-48 lg:w-64 md:border-b-0 md:border-r">
            <label class="px-4 font-semibold text-gray-500" for="from">From</label>
            <Select prompt="Departing Location" :options="departures" />
          </div>
          <div class="py-6 border-b md:py-4 md:w-48 lg:w-64 md:border-b-0 md:border-r">
            <label class="px-4 font-semibold text-gray-500" for="to">To</label>
            <Select prompt="Destination" :options="arrivals" />
          </div>
          <div class="py-6 md:py-4 md:w-48 lg:w-64">
            <label class="px-4 font-semibold text-gray-500" for="from">When</label>
            <svg class="w-6 h-6 mt-1 ml-3 fill-current" viewBox="0 0 24 24">
              <defs />
              <path
                class="heroicon-ui"
                d="M17 4h2a2 2 0 012 2v14a2 2 0 01-2 2H5a2 2 0 01-2-2V6c0-1.1.9-2 2-2h2V3a1 1 0 112 0v1h6V3a1 1 0 012 0v1zm-2 2H9v1a1 1 0 11-2 0V6H5v4h14V6h-2v1a1 1 0 01-2 0V6zm4 6H5v8h14v-8z"
              />
            </svg>
          </div>
          <a
            href="#"
            class="flex items-center justify-center inline-block px-6 py-5 text-xl font-semibold text-white bg-red-500 rounded-b-lg md:px-10 focus:outline-none focus:shadow-outline md:rounded-b-none md:rounded-r-lg"
          >Search</a>
        </form>
      </div>
    </section>
    <section class="flex flex-wrap px-4 pt-8 bg-gray-200 lg:justify-center">
      <div class="w-full px-2 lg:hidden">
        <a
          class="text-xl text-blue-500 cursor-pointer"
          @click="showFilters = !showFilters"
        >{{ showFilters ? 'Hide Filters' : 'Filter Destinations &#8250;' }}</a>
      </div>
      <div class="self-start w-full max-w-sm px-2 lg:block lg:w-1/3 lg:mt-0">
        <h1 class="hidden text-2xl font-semibold lg:block">Filters</h1>
        <Filters class="lg:block" :class="showFilters ? 'block' : 'hidden'" />
        <div class="relative hidden h-64 mt-4 overflow-hidden rounded-lg lg:block">
          <img
            class="absolute inset-0 object-cover h-full rounded-lg"
            src="https://images.unsplash.com/photo-1486868451447-83c6bf387a38?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=600&q=80"
          />
          <div class="absolute inset-0 bg-red-300 rounded-lg opacity-25"></div>
          <div class="absolute inset-0 flex flex-col items-center justify-between">
            <span
              class="mt-5 text-lg font-semibold text-center text-white uppercase"
            >Discover the Perfect Honeymoon</span>
            <a
              class="px-8 py-2 mb-8 text-sm font-semibold text-white bg-red-500 rounded-lg"
              href="#"
            >More</a>
          </div>
        </div>
      </div>
      <div class="self-center w-full max-w-6xl px-2 pb-8 mt-5 lg:w-2/3 lg:mt-0">
        <span class="text-2xl font-semibold">Popular Destinations</span>
        <div class="mt-4" v-for="(destination, index) in destinations" :key="index">
          <DestinationCard :destination="destination" />
        </div>
      </div>
    </section>
    <Footer />
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
import Select from "./components/Select";
import Filters from "./components/Filters";
import DestinationCard from "./components/DestinationCard";
import Footer from "./components/Footer";
export default {
  name: "app",
  components: {
    Navbar,
    Select,
    Filters,
    DestinationCard,
    Footer
  },
  data() {
    return {
      showFilters: false,
      departures: [
        "Los Angeles, CA",
        "Dallas, TX",
        "Chicago, IL",
        "Cincinnati, OH",
        "Seattle, WA"
      ],
      arrivals: [
        "Tokyo, JP",
        "London, UK",
        "Cape Town, SA",
        "Melbourne, AU",
        "Phuket, TH"
      ],
      destinations: [
        {
          location: "Phuket",
          country: "Thailand",
          rating: 5,
          reviews: 275,
          duration: "6 Nights, 7 Days",
          hotel: "5 Star Hotel",
          activities: 33,
          flightType: "Coach",
          price: 875,
          image:
            "https://images.unsplash.com/photo-1551418843-01c6b62e864d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80"
        },
        {
          location: "Los Angeles, CA",
          country: "United States",
          rating: 3,
          reviews: 85,
          duration: "4 Nights, 5 Days",
          hotel: "3 Star Hotel",
          activities: 16,
          flightType: "Coach",
          price: 650,
          image:
            "https://images.unsplash.com/photo-1429554429301-1c7d5ae2d42e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80"
        },
        {
          location: "Tokyo",
          country: "Japan",
          rating: 5,
          reviews: 126,
          duration: "6 Nights, 5 Days",
          hotel: "5 Star Hotel",
          activities: 38,
          flightType: "First Class",
          price: 1375,
          image:
            "https://images.unsplash.com/photo-1558632328-465f59aff245?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80"
        },
        {
          location: "Chicago, IL",
          country: "United States",
          rating: 3,
          reviews: 112,
          duration: "3 Nights, 4 Days",
          hotel: "3 Star Hotel",
          activities: 19,
          flightType: "Economy",
          price: 565,
          image:
            "https://images.unsplash.com/photo-1494522358652-f30e61a60313?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80"
        },
        {
          location: "London",
          country: "United Kingdom",
          rating: 4,
          reviews: 67,
          duration: "6 Nights, 7 Days",
          hotel: "4 Star Hotel",
          activities: 25,
          flightType: "Economy Plus",
          price: 1250,
          image:
            "https://images.unsplash.com/photo-1505761671935-60b3a7427bad?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80"
        },
        {
          location: "Cape Town",
          country: "South Africa",
          rating: 3,
          reviews: 113,
          duration: "3 Nights, 4 Days",
          hotel: "3 Star Hotel",
          activities: 22,
          flightType: "First Class",
          price: 1525,
          image:
            "https://images.unsplash.com/photo-1543261534-09e5f83a86c2?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80"
        },
        {
          location: "Melbourne",
          country: "Australia",
          rating: 4,
          reviews: 176,
          duration: "4 Nights, 5 Days",
          hotel: "4 Star Hotel",
          activities: 27,
          flightType: "Economy",
          price: 1025,
          image:
            "https://images.unsplash.com/photo-1545044846-351ba102b6d5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80"
        }
      ]
    };
  }
};
</script>

<style src="./css/tailwind.css"/>
