<template>
  <Teleport to="body">
    <Transition
      enter-active-class="transition-all duration-300 ease-out"
      enter-from-class="opacity-0 scale-75"
      enter-to-class="opacity-100 scale-100"
      leave-active-class="transition-all duration-300 ease-in"
      leave-from-class="opacity-100 scale-100"
      leave-to-class="opacity-0 scale-75"
    >
      <div
        v-if="showProgress"
        class="fixed bottom-8 right-8 z-50"
      >
        <button
          @click="scrollToTop"
          class="relative w-16 h-16 bg-white rounded-full shadow-lg flex items-center justify-center hover:bg-emerald-50 transition-colors border border-emerald-200 group"
        >
          <!-- SVG Circle Progress -->
          <svg class="absolute inset-0 w-16 h-16 -rotate-90">
            <!-- Background circle -->
            <circle
              cx="32"
              cy="32"
              r="28"
              stroke="#e5e7eb"
              stroke-width="3"
              fill="none"
            />
            <!-- Progress circle -->
            <circle
              cx="32"
              cy="32"
              r="28"
              :stroke="progressColor"
              stroke-width="3"
              fill="none"
              :stroke-dasharray="circumference"
              :stroke-dashoffset="dashOffset"
              stroke-linecap="round"
              class="transition-all duration-300 ease-out"
            />
          </svg>
          
          <!-- Arrow Icon -->
          <svg
            class="w-6 h-6 text-emerald-500 relative z-10 group-hover:text-emerald-600 transition-colors"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M5 10l7-7m0 0l7 7m-7-7v18"
            />
          </svg>
        </button>
      </div>
    </Transition>
  </Teleport>
</template>

<script setup lang="ts">
const showProgress = ref(false)
const scrollProgress = ref(0)
const progressColor = ref('#10b981') // emerald-500

const radius = 28
const circumference = 2 * Math.PI * radius

const dashOffset = computed(() => {
  return circumference - (scrollProgress.value / 100) * circumference
})

const updateScrollProgress = () => {
  const windowHeight = window.innerHeight
  const documentHeight = document.documentElement.scrollHeight - windowHeight
  const scrollTop = window.scrollY
  
  const progress = (scrollTop / documentHeight) * 100
  scrollProgress.value = Math.min(Math.max(progress, 0), 100)
  
  showProgress.value = scrollTop > windowHeight * 0.5
  
  if (progress < 33) {
    progressColor.value = '#10b981' // emerald-500
  } else if (progress < 66) {
    progressColor.value = '#3b82f6' // blue-500
  } else {
    progressColor.value = '#8b5cf6' // purple-500
  }
}

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

onMounted(() => {
  window.addEventListener('scroll', updateScrollProgress)
  updateScrollProgress()
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', updateScrollProgress)
})
</script>

<style scoped>
svg circle {
  transition: stroke-dashoffset 0.3s ease-out, stroke 0.3s ease-out;
}
</style>