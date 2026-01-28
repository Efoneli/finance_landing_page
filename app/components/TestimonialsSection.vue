<template>
  <section class="py-24 bg-gradient-to-b from-gray-50 to-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Testimonial Card -->
      <div class="bg-white rounded-3xl shadow-xl p-12 md:p-16 relative overflow-hidden">
        <!-- Decorative curved shape -->
        <div class="absolute top-0 left-0 w-96 h-96 -translate-x-32 -translate-y-32">
          <svg viewBox="0 0 400 400" fill="none" class="w-full h-full">
            <path 
              d="M 0 200 Q 150 100, 300 200 L 300 400 L 0 400 Z" 
              fill="#10b981" 
              opacity="0.8"
            />
            <path 
              d="M 100 250 Q 200 150, 350 250 L 350 400 L 100 400 Z" 
              fill="#1a1f2e" 
              opacity="0.9"
            />
          </svg>
        </div>

        <div class="relative grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
          <!-- Left - Image with green circle background -->
          <div class="flex justify-center lg:justify-start">
            <div class="relative">
              <!-- Green circle background -->
               <div class="bg-emerald-900 pr-8 pt-1 rounded-t-full">
              <div class="w-80 h-80 bg-emerald-300 rounded-t-full overflow-hidden relative">
                <TransitionGroup name="fade">
                  <img 
                    v-if="currentTestimonial === 0"
                    key="person-0"
                    src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=500&h=500&fit=crop"
                    alt="Dennis Lail"
                    class="absolute inset-0 w-full h-full object-cover"
                  />
                  <img 
                    v-if="currentTestimonial === 1"
                    key="person-1"
                    src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=500&h=500&fit=crop"
                    alt="Sarah Johnson"
                    class="absolute inset-0 w-full h-full object-cover"
                  />
                  <img 
                    v-if="currentTestimonial === 2"
                    key="person-2"
                    src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?w=500&h=500&fit=crop"
                    alt="Michael Chen"
                    class="absolute inset-0 w-full h-full object-cover"
                  />
                </TransitionGroup>
              </div>
            </div>
            </div>
          </div>

          <!-- Right - Testimonial Content -->
          <div class="space-y-6">
            <!-- Quote Icon -->
            <div class="w-16 h-16 bg-emerald-400 rounded-full flex items-center justify-center">
              <svg class="w-8 h-8 text-white" fill="currentColor" viewBox="0 0 24 24">
                <path d="M14.017 21v-7.391c0-5.704 3.731-9.57 8.983-10.609l.995 2.151c-2.432.917-3.995 3.638-3.995 5.849h4v10h-9.983zm-14.017 0v-7.391c0-5.704 3.748-9.57 9-10.609l.996 2.151c-2.433.917-3.996 3.638-3.996 5.849h3.983v10h-9.983z"/>
              </svg>
            </div>

            <!-- Testimonial Text (Changes with fade) -->
            <div class="relative min-h-[200px]">
              <TransitionGroup name="slide-up">
                <div
                  v-if="currentTestimonial === 0"
                  key="testimonial-0"
                  class="absolute inset-0"
                >
                  <p class="text-xl md:text-2xl text-gray-800 leading-relaxed mb-8">
                    Making this the first true 😍 generator on the Internet. It uses a dictionary of over words, combined with a handful of model sentence structures, to generate 👍👍
                  </p>
                  <div>
                    <h4 class="text-2xl font-bold text-gray-900">Dennis Lail</h4>
                    <p class="text-gray-600">Marketer</p>
                  </div>
                </div>

                <div
                  v-if="currentTestimonial === 1"
                  key="testimonial-1"
                  class="absolute inset-0"
                >
                  <p class="text-xl md:text-2xl text-gray-800 leading-relaxed mb-8">
                    An incredible platform that has transformed how we work. The team is responsive and the features are exactly what we needed for our business growth 🚀
                  </p>
                  <div>
                    <h4 class="text-2xl font-bold text-gray-900">Sarah Johnson</h4>
                    <p class="text-gray-600">CEO, TechStart</p>
                  </div>
                </div>

                <div
                  v-if="currentTestimonial === 2"
                  key="testimonial-2"
                  class="absolute inset-0"
                >
                  <p class="text-xl md:text-2xl text-gray-800 leading-relaxed mb-8">
                    The best investment we've made for our company. Easy to use, powerful features, and outstanding customer support. Highly recommend! ⭐⭐⭐⭐⭐
                  </p>
                  <div>
                    <h4 class="text-2xl font-bold text-gray-900">Michael Chen</h4>
                    <p class="text-gray-600">Founder, Innovate Labs</p>
                  </div>
                </div>
              </TransitionGroup>
            </div>
          </div>
        </div>

        <!-- Progress Bar at Bottom -->
        <div class="relative mt-12">
          <div class="h-1 bg-gray-200 rounded-full overflow-hidden">
            <div
              class="h-full bg-emerald-400 rounded-full transition-all"
              :style="{ 
                width: `${progress}%`,
                transitionDuration: isResetting ? '0ms' : '100ms'
              }"
            />
          </div>
        </div>

        <!-- Company Logos -->
        <div class="mt-16 pt-8 border-t border-gray-200">
          <div class="flex flex-wrap items-center justify-center gap-12 opacity-40">
            <!-- jQuery -->
            <div class="grayscale hover:grayscale-0 transition-all">
              <svg class="h-8" viewBox="0 0 120 30" fill="currentColor">
                <text x="0" y="20" font-family="Arial, sans-serif" font-size="20" font-weight="bold">jQuery</text>
              </svg>
            </div>
            
            <!-- GitHub -->
            <div class="grayscale hover:grayscale-0 transition-all">
              <svg class="h-8" viewBox="0 0 120 30" fill="currentColor">
                <text x="0" y="20" font-family="Arial, sans-serif" font-size="20" font-weight="bold">GitHub</text>
              </svg>
            </div>
            
            <!-- Portis -->
            <div class="grayscale hover:grayscale-0 transition-all">
              <svg class="h-8" viewBox="0 0 120 30" fill="currentColor">
                <text x="0" y="20" font-family="Arial, sans-serif" font-size="20" font-style="italic">Portis</text>
              </svg>
            </div>
            
            <!-- Envato -->
            <div class="grayscale hover:grayscale-0 transition-all">
              <svg class="h-8" viewBox="0 0 120 30" fill="currentColor">
                <text x="0" y="20" font-family="Arial, sans-serif" font-size="20">envato</text>
              </svg>
            </div>
            
            <!-- Dropmak -->
            <div class="grayscale hover:grayscale-0 transition-all">
              <svg class="h-8" viewBox="0 0 120 30" fill="currentColor">
                <text x="0" y="20" font-family="Arial, sans-serif" font-size="20">dropmak</text>
              </svg>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const currentTestimonial = ref(0)
const totalTestimonials = 3
const progress = ref(0)
const isResetting = ref(false)
const animationDuration = 5000 // 5 seconds per testimonial

let animationFrameId: number | null = null
let startTime: number | null = null

const animate = (timestamp: number) => {
  if (!startTime) startTime = timestamp
  
  const elapsed = timestamp - startTime
  const newProgress = Math.min((elapsed / animationDuration) * 100, 100)
  
  progress.value = newProgress
  
  if (newProgress < 100) {
    animationFrameId = requestAnimationFrame(animate)
  } else {
    // Progress complete - change testimonial
    setTimeout(() => {
      currentTestimonial.value = (currentTestimonial.value + 1) % totalTestimonials
      
      // Reset progress bar instantly
      isResetting.value = true
      progress.value = 0
      
      // Start next cycle
      setTimeout(() => {
        isResetting.value = false
        startTime = null
        animationFrameId = requestAnimationFrame(animate)
      }, 50)
    }, 200)
  }
}

const stopAnimation = () => {
  if (animationFrameId !== null) {
    cancelAnimationFrame(animationFrameId)
    animationFrameId = null
  }
  startTime = null
}

onMounted(() => {
  animationFrameId = requestAnimationFrame(animate)
})

onBeforeUnmount(() => {
  stopAnimation()
})
</script>

<style scoped>
/* Fade transition for images */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

/* Slide up transition for testimonial text */
.slide-up-enter-active {
  transition: all 0.6s ease;
}

.slide-up-leave-active {
  transition: all 0.6s ease;
}

.slide-up-enter-from {
  opacity: 0;
  transform: translateY(20px);
}

.slide-up-leave-to {
  opacity: 0;
  transform: translateY(-20px);
}
</style>