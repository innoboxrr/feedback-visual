<template>
  <aside
    v-show="visible"
    class="w-96 h-full bg-white border-l border-gray-200 p-6 shadow-lg overflow-y-auto transition-all duration-300 z-[9999]"
  >
    <div class="flex justify-between items-center mb-4">
      <h2 class="text-lg font-bold">Enviar Feedback</h2>
      <button @click="visible = false" class="text-gray-500 hover:text-red-500">
        ✖
      </button>
    </div>
    <p class="text-sm text-gray-600">
      Este es el panel de feedback visual. Aún no tiene funcionalidad.
    </p>
  </aside>
</template>

<script>
export default {
  name: "FeedbackAside",
  data() {
    return {
      visible: false,
    };
  },
  mounted() {
    window.addEventListener("toggleFeedback", this.toggleFeedbackVisibility);
  },
  beforeUnmount() {
    window.removeEventListener("toggleFeedback", this.toggleFeedbackVisibility);
  },
  methods: {
    toggleFeedbackVisibility() {
      this.visible = !this.visible;
    },
  },
};
</script>
