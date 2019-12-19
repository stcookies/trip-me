<template>
  <div>
    <div class="flex flex-col flex-wrap p-8 mt-4 bg-white rounded-lg shadow">
      <span class="text-lg font-semibold text-gray-800">Categories</span>
      <div class="flex flex-wrap items-center justify-between pt-3">
        <label class="w-full sm:w-1/2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="text-md">Honeymoon</span>
        </label>
        <label class="w-full pt-2 sm:pt-0 sm:w-1/2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="text-md">Family</span>
        </label>
        <label class="w-full pt-2 sm:w-1/2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="text-md">Friends</span>
        </label>
      </div>
      <span class="block pt-8 text-lg font-semibold text-gray-800">Days</span>
      <div class="flex flex-wrap items-center justify-between pt-3">
        <label class="w-full sm:w-1/2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="text-md">1-2</span>
        </label>
        <label class="w-full pt-2 sm:pt-0 sm:w-1/2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="text-md">3-5</span>
        </label>
        <label class="w-full pt-2 sm:w-1/2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="text-md">6-8</span>
        </label>
        <label class="w-full pt-2 sm:w-1/2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="text-md">8-10</span>
        </label>
        <label class="w-full pt-2 sm:w-1/2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="text-md">11+</span>
        </label>
      </div>
      <span class="block pt-8 text-lg font-semibold text-gray-800">Budget (USD)</span>
      <div class="flex flex-wrap pt-3">
        <label class="w-full sm:w-1/2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="text-md">0-1000</span>
        </label>
        <label class="w-full pt-2 sm:pt-0 sm:w-1/2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="text-md">1000-2500</span>
        </label>
        <label class="w-full pt-2 sm:w-1/2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="text-md">2500-5000</span>
        </label>
        <label class="w-full pt-2 sm:w-1/2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="text-md">5000-7500</span>
        </label>
        <label class="w-full pt-2 sm:w-1/2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="text-md">7500-10,000</span>
        </label>
        <label class="w-full pt-2 sm:w-1/2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="text-md">10,000+</span>
        </label>
      </div>
      <span class="block pt-8 text-lg font-semibold text-gray-800">Hotel Rating</span>
      <div class="pt-3">
        <label class="flex items-center">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="pr-2 text-md">5 star</span>
          <svg v-for="i in 5" :key="i" viewBox="0 0 24 24" :class="i <= 5 ? 'text-yellow-400' : 'text-gray-400'" class="w-4 h-4 fill-current">
            <path d="M8.128 19.825a1.586 1.586 0 0 1-1.643-.117 1.543 1.543 0 0 1-.53-.662 1.515 1.515 0 0 1-.096-.837l.736-4.247-3.13-3a1.514 1.514 0 0 1-.39-1.569c.09-.271.254-.513.475-.698.22-.185.49-.306.776-.35L8.66 7.73l1.925-3.862c.128-.26.328-.48.577-.633a1.584 1.584 0 0 1 1.662 0c.25.153.45.373.577.633l1.925 3.847 4.334.615c.29.042.562.162.785.348.224.186.39.43.48.704a1.514 1.514 0 0 1-.404 1.58l-3.13 3 .736 4.247c.047.282.014.572-.096.837-.111.265-.294.494-.53.662a1.582 1.582 0 0 1-1.643.117l-3.865-2-3.865 2z" />
          </svg>
        </label>
        <label class="flex items-center pt-2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="pr-2 text-md">4 star</span>
          <svg v-for="i in 5" :key="i" viewBox="0 0 24 24" :class="i <= 4 ? 'text-yellow-400' : 'text-gray-400'" class="w-4 h-4 fill-current">
            <path d="M8.128 19.825a1.586 1.586 0 0 1-1.643-.117 1.543 1.543 0 0 1-.53-.662 1.515 1.515 0 0 1-.096-.837l.736-4.247-3.13-3a1.514 1.514 0 0 1-.39-1.569c.09-.271.254-.513.475-.698.22-.185.49-.306.776-.35L8.66 7.73l1.925-3.862c.128-.26.328-.48.577-.633a1.584 1.584 0 0 1 1.662 0c.25.153.45.373.577.633l1.925 3.847 4.334.615c.29.042.562.162.785.348.224.186.39.43.48.704a1.514 1.514 0 0 1-.404 1.58l-3.13 3 .736 4.247c.047.282.014.572-.096.837-.111.265-.294.494-.53.662a1.582 1.582 0 0 1-1.643.117l-3.865-2-3.865 2z" />
          </svg>
        </label>
        <label class="flex items-center pt-2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="pr-2 text-md">3 star</span>
          <svg v-for="i in 5" :key="i" viewBox="0 0 24 24" :class="i <= 3 ? 'text-yellow-400' : 'text-gray-400'" class="w-4 h-4 fill-current">
            <path d="M8.128 19.825a1.586 1.586 0 0 1-1.643-.117 1.543 1.543 0 0 1-.53-.662 1.515 1.515 0 0 1-.096-.837l.736-4.247-3.13-3a1.514 1.514 0 0 1-.39-1.569c.09-.271.254-.513.475-.698.22-.185.49-.306.776-.35L8.66 7.73l1.925-3.862c.128-.26.328-.48.577-.633a1.584 1.584 0 0 1 1.662 0c.25.153.45.373.577.633l1.925 3.847 4.334.615c.29.042.562.162.785.348.224.186.39.43.48.704a1.514 1.514 0 0 1-.404 1.58l-3.13 3 .736 4.247c.047.282.014.572-.096.837-.111.265-.294.494-.53.662a1.582 1.582 0 0 1-1.643.117l-3.865-2-3.865 2z" />
          </svg>
        </label>
        <label class="flex items-center pt-2">
          <input class="w-5 h-5 mr-2 leading-tight form-checkbox" type="checkbox">
          <span class="pr-2 text-md">2 star</span>
          <svg v-for="i in 5" :key="i" viewBox="0 0 24 24" :class="i <= 2 ? 'text-yellow-400' : 'text-gray-400'" class="w-4 h-4 fill-current">
            <path d="M8.128 19.825a1.586 1.586 0 0 1-1.643-.117 1.543 1.543 0 0 1-.53-.662 1.515 1.515 0 0 1-.096-.837l.736-4.247-3.13-3a1.514 1.514 0 0 1-.39-1.569c.09-.271.254-.513.475-.698.22-.185.49-.306.776-.35L8.66 7.73l1.925-3.862c.128-.26.328-.48.577-.633a1.584 1.584 0 0 1 1.662 0c.25.153.45.373.577.633l1.925 3.847 4.334.615c.29.042.562.162.785.348.224.186.39.43.48.704a1.514 1.514 0 0 1-.404 1.58l-3.13 3 .736 4.247c.047.282.014.572-.096.837-.111.265-.294.494-.53.662a1.582 1.582 0 0 1-1.643.117l-3.865-2-3.865 2z" />
          </svg>
        </label>
      </div>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style>
</style>