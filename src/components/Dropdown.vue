<template>
  <div class="relative">
    <span tabindex="1" @click="isOpen = !isOpen" class="w-full px-4 mt-1 pr-3 focus:outline-none focus:shadow-outline font-semibold block cursor-pointer">{{ selection || prompt }}</span>
    <button v-if="isOpen" @click="isOpen = false" tabindex="-1" class="fixed z-30 inset-0 h-full w-full opacity-0 cursor-default"></button>
    <div v-if="isOpen" class="absolute z-40 mt-2 py-2 w-full bg-white rounded-b-lg shadow-2xl">
      <a @click="selection = option" v-for="(option, index) in options" :key="index" href="#" class="block px-4 py-2 hover:bg-red-500 hover:text-white">{{ option }}</a>
    </div>
  </div>
</template>

<script>
export default {
  props: ['prompt', 'options'],
  data() {
    return {
      isOpen: false,
      selection: null
    }
  },
  watch: {
    selection() {
      this.isOpen = false;
      this.$emit('selected', this.selection);
    }
  }
}
</script>

<style>
</style>