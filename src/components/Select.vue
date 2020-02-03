<template>
  <div class="relative">
    <span
      tabindex="1"
      @click="isOpen = !isOpen"
      class="block w-full px-4 pr-3 mt-1 font-semibold cursor-pointer focus:outline-none focus:shadow-outline"
      >{{ selection || prompt }}</span
    >
    <button
      v-if="isOpen"
      @click="isOpen = false"
      tabindex="-1"
      class="fixed inset-0 z-30 w-full h-full opacity-0 cursor-default"
    ></button>
    <div
      v-if="isOpen"
      class="absolute z-40 w-full py-2 mt-2 bg-white rounded-b-lg shadow-2xl"
    >
      <a
        @click="selection = option"
        v-for="(option, index) in options"
        :key="index"
        href="#"
        class="block px-4 py-2 hover:bg-red-500 hover:text-white"
        >{{ option }}</a
      >
    </div>
  </div>
</template>

<script>
export default {
  props: ["prompt", "options"],
  data() {
    return {
      isOpen: false,
      selection: null
    };
  },
  watch: {
    selection() {
      this.isOpen = false;
      this.$emit("selected", this.selection);
    }
  }
};
</script>

<style></style>
