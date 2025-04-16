<template>
  <div id="AppWrapper" class="flex w-full h-screen overflow-hidden">
      <div class="flex-1 overflow-auto p-6">
          <HelloWorld />
      </div>
      <FeedbackAside v-if="showFeedback" />
  </div>
</template>

<script setup>
import HelloWorld from './components/HelloWorld.vue'
import FeedbackAside from './feedback-component/FeedbackAside.vue'
import { ref, onMounted, onBeforeUnmount } from 'vue'

const showFeedback = ref(false)

function toggleFeedback() {
  showFeedback.value = !showFeedback.value
}

onMounted(() => {
  window.addEventListener('toggleFeedback', toggleFeedback)
})

onBeforeUnmount(() => {
  window.removeEventListener('toggleFeedback', toggleFeedback)
})
</script>