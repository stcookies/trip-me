<template>
  <header class="sticky top-0 z-20 bg-white shadow sm:flex sm:justify-between sm:items-center sm:px-8 sm:py-5">
    <div class="flex items-center justify-between px-4 py-5 sm:p-0">
      <a tabindex="-1" href="#">
        <img class="inline-block h-8" src="../assets/img/logo.svg" alt="Trip Me Logo">
        <span class="pl-3 font-semibold text-red-500">Trip Me</span>
      </a>
      <div class="sm:hidden">
        <button @click="isOpen = !isOpen" type="button" class="block focus:outline-none">
          <svg class="h-6 w-6 fill-current" viewBox="0 0 24 24">
            <path v-if="isOpen" fill-rule="evenodd" d="M18.278 16.864a1 1 0 0 1-1.414 1.414l-4.829-4.828-4.828 4.828a1 1 0 0 1-1.414-1.414l4.828-4.829-4.828-4.828a1 1 0 0 1 1.414-1.414l4.829 4.828 4.828-4.828a1 1 0 1 1 1.414 1.414l-4.828 4.829 4.828 4.828z"/>
            <path v-if="!isOpen" fill-rule="evenodd" d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"/>
          </svg>
        </button>
      </div>
    </div>
    <nav :class="isOpen ? 'block' : 'hidden'" class="sm:block">
      <div class="px-2 pt-2 pb-4 sm:flex sm:p-0">
        <a href="#" class="block px-2 py-1 hover:text-red-500 sm:mt-0 sm:ml-2">Tours</a>
        <a href="#" class="mt-1 block px-2 py-1 hover:text-red-500 sm:mt-0 sm:ml-2">Offers</a>
        <a href="#" class="mt-1 block px-2 py-1 hover:text-red-500 sm:mt-0 sm:ml-2">About</a>
        <a href="#" class="mt-1 block px-2 py-1 hover:text-red-500 sm:mt-0 sm:ml-2">Contact</a>
        <AccountDropdown class="hidden sm:block sm:ml-6"/>
      </div>
      <div class="px-4 py-5 border-t border-gray-300 sm:hidden">
        <div class="flex items-center">
          <img class="h-8 w-8 border-2 border-gray-600 rounded-full object-cover" src="https://images.unsplash.com/photo-1553907725-c3d2e2ccc00e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=668&q=80" alt="Your avatar">
          <span class="ml-3 font-semibold text-white">Jane Doe</span>
        </div>
        <div class="mt-4">
          <a href="#" class="block">Account settings</a>
          <a href="#" class="mt-2 block">Support</a>
          <a href="#" class="mt-2 block">Sign out</a>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
import AccountDropdown from './AccountDropdown'
export default {
  components: {
    AccountDropdown
  },
  data() {
    return {
      isOpen: false
    }
  }
}
</script>

<style>
</style>