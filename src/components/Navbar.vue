<template>
  <header class="sticky top-0 z-20 px-2 bg-white shadow sm:px-8">
    <div
      class="max-w-6xl mx-auto sm:flex sm:justify-between sm:items-center sm:py-5"
    >
      <div class="flex items-center justify-between px-4 py-5 sm:p-0">
        <a class="flex items-center" tabindex="-1" href="#">
          <svg class="h-8 text-red-500 fill-current" viewBox="0 0 64 36.6">
            <path
              d="M32 29.1c-5.6 4-13.5 5.2-19.8 1.8-4.2-2.2-7.4-6.8-9.2-11 1.2 5.4 4.6 10.3 9.8 13 7.5 4 16.1 2.2 21-3.9-.9-.2-.9.2-1.8.1z"
            />
            <path
              class="st1"
              d="M39.2 26.6L59.4 7.4c1.2-1.2 2.2-4 1.2-5-1.1-1.1-3.8 0-5 1.2L36.3 23.7l2.9 2.9z"
            />
            <path
              class="st1"
              d="M48.3 11.3c-.8-.3-16-5.2-16-5.2l-4.2 3.5 14.3 7.9 5.9-6.2z"
            />
            <path
              class="st1"
              d="M39.1 12.1c-.7.7-2 .7-2.8-.1-.8-.8-.9-2.1-.1-2.8L39.4 6c.7-.7 2-.7 2.8.1.8.8.9 2.1.1 2.8l-3.2 3.2zM51.6 14.5c.3.8 5.2 16 5.2 16l-3.5 4.2-7.9-14.3 6.2-5.9z"
            />
            <path
              class="st1"
              d="M50.8 23.8c-.7.7-.7 2 .1 2.8.8.8 2.1.9 2.8.1l3.2-3.2c.7-.7.7-2-.1-2.8-.8-.8-2.1-.9-2.8-.1l-3.2 3.2zM33.7 29.9c-.2.2-.5.2-.7 0-.2-.2-.2-.5 0-.7l5.9-5.9c.2-.2.5-.2.7 0 .2.2.2.5 0 .7l-5.9 5.9z"
            />
            <g>
              <path
                class="st1"
                d="M39.6 22.9c-.3.1-7.9.6-7.9.6l-3 2.9 6.3 1.3 4.6-4.8zM39.7 23.5c0 .3-.6 7.9-.6 7.9l-2.9 3-1.2-6.3 4.7-4.6z"
              />
            </g>
          </svg>
          <span class="pl-3 font-semibold text-red-500">Trip Me</span>
        </a>
        <div class="sm:hidden">
          <button
            @click="isOpen = !isOpen"
            type="button"
            class="block focus:outline-none"
          >
            <svg class="w-6 h-6 fill-current" viewBox="0 0 24 24">
              <path
                v-if="isOpen"
                fill-rule="evenodd"
                d="M18.278 16.864a1 1 0 0 1-1.414 1.414l-4.829-4.828-4.828 4.828a1 1 0 0 1-1.414-1.414l4.828-4.829-4.828-4.828a1 1 0 0 1 1.414-1.414l4.829 4.828 4.828-4.828a1 1 0 1 1 1.414 1.414l-4.828 4.829 4.828 4.828z"
              />
              <path
                v-if="!isOpen"
                fill-rule="evenodd"
                d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
              />
            </svg>
          </button>
        </div>
      </div>
      <nav :class="isOpen ? 'block' : 'hidden'" class="sm:block">
        <div class="px-2 pt-2 pb-4 sm:flex sm:p-0">
          <a href="#" class="block px-2 py-1 hover:text-red-500 sm:mt-0 sm:ml-2"
            >Tours</a
          >
          <a
            href="#"
            class="block px-2 py-1 mt-1 hover:text-red-500 sm:mt-0 sm:ml-2"
            >Offers</a
          >
          <a
            href="#"
            class="block px-2 py-1 mt-1 hover:text-red-500 sm:mt-0 sm:ml-2"
            >About</a
          >
          <a
            href="#"
            class="block px-2 py-1 mt-1 hover:text-red-500 sm:mt-0 sm:ml-2"
            >Contact</a
          >
          <AccountDropdown class="hidden sm:block sm:ml-6" />
        </div>
        <div class="px-4 py-5 border-t border-gray-300 sm:hidden">
          <div class="flex items-center">
            <img
              class="object-cover w-8 h-8 border-2 border-gray-600 rounded-full"
              src="https://images.unsplash.com/photo-1553907725-c3d2e2ccc00e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=668&q=80"
              alt="Your avatar"
            />
            <span class="ml-3 font-semibold text-white">Jane Doe</span>
          </div>
          <div class="mt-4">
            <a href="#" class="block">Account settings</a>
            <a href="#" class="block mt-2">Support</a>
            <a href="#" class="block mt-2">Sign out</a>
          </div>
        </div>
      </nav>
    </div>
  </header>
</template>

<script>
import AccountDropdown from "./AccountDropdown";
export default {
  components: {
    AccountDropdown
  },
  data() {
    return {
      isOpen: false
    };
  }
};
</script>

<style></style>
