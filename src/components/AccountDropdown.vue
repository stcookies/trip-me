<template>
  <div class="relative">
    <button @click="isOpen = !isOpen" class="relative z-30 block h-8 w-8 rounded-full overflow-hidden focus:outline-none focus:border focus:shadow-outline">
      <img class="h-full w-full object-cover" src="https://images.unsplash.com/photo-1553907725-c3d2e2ccc00e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=668&q=80" alt="Your avatar">
    </button>
    <button v-if="isOpen" @click="isOpen = false" tabindex="-1" class="fixed inset-0 h-full w-full opacity-0 cursor-default"></button>
    <div v-if="isOpen" class="absolute right-0 mt-2 py-2 w-48 border bg-white rounded-lg shadow-2xl">
      <a href="#" class="block px-4 py-2 hover:bg-red-500 hover:text-white">Account settings</a>
      <a href="#" class="block px-4 py-2 hover:bg-red-500 hover:text-white">Support</a>
      <a href="#" class="block px-4 py-2 hover:bg-red-500 hover:text-white">Sign out</a>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false
    }
  },
  created() {
    const handleEscape = (e) => {
      if (e.key === 'Esc' || e.key === 'Escape') {
        this.isOpen = false;
      }
    }
    document.addEventListener('keydown', handleEscape);
    this.$once('hook:beforeDestroy', () => {
      document.removeEventListener('keydown', handleEscape);
    });
  }
}
</script>

<style>
</style>