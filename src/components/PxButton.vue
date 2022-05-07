<template>
  <button
    @click="buttonClick"
    class="bg-purple-500 hover:bg-black-700 text-black font-bold py-2 px-4 rounded-full"
  >
    <beat-loader :loading="isLoading" :color="'#68d391'" :size="8" />

    <p v-show="!isLoading">
      <slot></slot>
    </p>
  </button>
</template>

<script>
export default {
  name: "PxButton",

  props: {
    isLoading: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    buttonClick() {
      this.$emit("custom-click");
    }
  }
};
</script>
