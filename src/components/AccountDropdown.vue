<template>
  <div class="relative">
    <button
      @click="isOpen = !isOpen"
      class="relative z-30 block w-8 h-8 overflow-hidden rounded-full focus:outline-none focus:border focus:shadow-outline"
    >
      <img
        class="object-cover w-full h-full"
        src="https://images.unsplash.com/photo-1553907725-c3d2e2ccc00e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=668&q=80"
        alt="Your avatar"
      />
    </button>
    <button
      v-if="isOpen"
      @click="isOpen = false"
      tabindex="-1"
      class="fixed inset-0 w-full h-full opacity-0 cursor-default"
    ></button>
    <div
      v-if="isOpen"
      class="absolute right-0 w-48 py-2 mt-2 bg-white border rounded-lg shadow-2xl"
    >
      <a href="#" class="block px-4 py-2 hover:bg-red-500 hover:text-white"
        >Account settings</a
      >
      <a href="#" class="block px-4 py-2 hover:bg-red-500 hover:text-white"
        >Support</a
      >
      <a href="#" class="block px-4 py-2 hover:bg-red-500 hover:text-white"
        >Sign out</a
      >
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false
    };
  },
  created() {
    const handleEscape = e => {
      if (e.key === "Esc" || e.key === "Escape") {
        this.isOpen = false;
      }
    };
    document.addEventListener("keydown", handleEscape);
    this.$once("hook:beforeDestroy", () => {
      document.removeEventListener("keydown", handleEscape);
    });
  }
};
</script>

<style></style>
