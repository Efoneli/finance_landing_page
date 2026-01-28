<template>
  <section class="relative min-h-screen bg-[#1a1f2e] overflow-hidden">
    <!-- Decorative Background Elements -->
    <div class="absolute inset-0 overflow-hidden">
      <!-- Green circles -->
      <div class="absolute top-20 left-20 w-32 h-32 bg-emerald-500/10 rounded-full blur-3xl" />
      <div class="absolute bottom-40 left-40 w-48 h-48 bg-emerald-500/5 rounded-full blur-3xl" />
      <div class="absolute top-40 right-40 w-40 h-40 bg-emerald-500/10 rounded-full blur-2xl" />
      <div class="absolute bottom-20 right-20 w-36 h-36 bg-emerald-500/5 rounded-full blur-3xl" />
      
      <!-- Curved lines -->
      <svg class="absolute top-0 right-0 w-1/3 h-full" viewBox="0 0 400 800" fill="none">
        <path 
          d="M 400 200 Q 300 400, 400 600" 
          stroke="rgb(16 185 129 / 0.3)" 
          stroke-width="3"
          fill="none"
        />
      </svg>
    </div>

    <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 pt-32 pb-16">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <!-- Left Content -->
        <div class="text-white space-y-8">
          <div>
            <h1 class="text-5xl md:text-6xl lg:text-7xl font-bold leading-tight mb-6">
              Financial Security<br />
              Made 
              <span class="relative inline-block">
                <span class="text-[#81864A] relative z-10">{{ currentWord }}</span>
                <!-- Animated underline -->
                <span 
                  class="absolute bottom-1 left-0 h-3 bg-[#81864A]"
                  :style="{ width: underlineWidth + '%' }"
                />
              </span>
            </h1>
            <p class="text-lg text-gray-300 max-w-xl">
              Staco is the dedicated platform for human management that helps to grow your startup business quickly
            </p>
          </div>

          <!-- CTA Buttons -->
          <div class="flex flex-wrap gap-4">
            <button class="px-8 py-4 bg-emerald-400 hover:bg-emerald-500 text-gray-900 font-semibold rounded-full transition-all duration-300 shadow-lg shadow-emerald-500/30 hover:shadow-emerald-500/50 hover:scale-105">
              Get Start For Free
            </button>
            <button class="px-8 py-4 border-2 border-gray-600 hover:border-emerald-400 text-white font-semibold rounded-full transition-all duration-300 flex items-center gap-2 group">
              Let's talk
              <svg class="w-5 h-5 group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
              </svg>
            </button>
          </div>
        </div>

        <!-- Right Content - Video -->
        <div class="relative">
          <div class="relative rounded-3xl overflow-hidden shadow-2xl">
            <video
              ref="videoRef"
              class="w-full h-auto rounded-3xl"
              :src="videoSrc"
              loop
              muted
              playsinline
              autoplay
            />
            
            <!-- Play/Pause Button -->
            <button
              @click="toggleVideo"
              class="absolute bottom-6 right-6 w-14 h-14 bg-white rounded-full flex items-center justify-center shadow-lg hover:scale-110 transition-transform"
            >
              <svg v-if="isPlaying" class="w-6 h-6 text-gray-900" fill="currentColor" viewBox="0 0 24 24">
                <path d="M6 4h4v16H6V4zm8 0h4v16h-4V4z"/>
              </svg>
              <svg v-else class="w-6 h-6 text-gray-900 ml-1" fill="currentColor" viewBox="0 0 24 24">
                <path d="M8 5v14l11-7z"/>
              </svg>
            </button>
          </div>

          <!-- Decorative curved line overlay -->
          <svg class="absolute -top-10 -right-10 w-48 h-48 pointer-events-none" viewBox="0 0 200 200" fill="none">
            <path 
              d="M 50 0 Q 150 50, 100 150" 
              stroke="rgb(16 185 129)" 
              stroke-width="4"
              fill="none"
            />
          </svg>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const words = ['Easier', 'Accountable', 'Reliable', 'Secure', 'Simple']
const currentWord = ref(words[0])
const currentIndex = ref(0)
const videoRef = ref<HTMLVideoElement | null>(null)
const isPlaying = ref(true)
const underlineWidth = ref(0)

const videoSrc = '/videos/hero-video.mp4'

let animationInterval: NodeJS.Timeout | null = null

const animateUnderlineAndChangeWord = () => {
  // Reset underline to 0
  underlineWidth.value = 0
  
  // Animate underline from 0 to 100% over 2 seconds
  const animationDuration = 2000 // 2 seconds
  const steps = 60 // 60 steps for smooth animation
  const stepDuration = animationDuration / steps
  const increment = 100 / steps
  
  let currentStep = 0
  
  const animate = () => {
    if (currentStep < steps) {
      underlineWidth.value += increment
      currentStep++
      setTimeout(animate, stepDuration)
    } else {
      // After underline completes, change the word
      setTimeout(() => {
        currentIndex.value = (currentIndex.value + 1) % words.length
        currentWord.value = words[currentIndex.value]
        
        // Start the next cycle after a brief pause
        setTimeout(() => {
          animateUnderlineAndChangeWord()
        }, 300)
      }, 200)
    }
  }
  
  animate()
}

onMounted(() => {
  // Start the animation cycle
  animateUnderlineAndChangeWord()
})

onBeforeUnmount(() => {
  if (animationInterval) {
    clearInterval(animationInterval)
  }
})

const toggleVideo = () => {
  if (videoRef.value) {
    if (isPlaying.value) {
      videoRef.value.pause()
    } else {
      videoRef.value.play()
    }
    isPlaying.value = !isPlaying.value
  }
}
</script>

<style scoped>
/* Smooth transition for underline width */
span {
  transition: width 0.03s linear;
}
</style>