<template>
  <section class="py-24 bg-white relative overflow-hidden">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <div class="relative">
          <div class="mb-8">
            <span
              class="text-emerald-400 font-semibold text-sm tracking-wider uppercase"
            >
              Why Choose Us
            </span>
          </div>

          <div class="relative min-h-[400px]">
            <TransitionGroup name="slide-fade">
              <div
                v-show="currentSlide === 0"
                v-if="currentSlide === 0"
                key="slide-0"
                class="absolute inset-0"
              >
                <h2
                  class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 leading-tight"
                >
                  Manage team increase productivity
                </h2>
                <p class="text-gray-600 text-lg mb-8 leading-relaxed">
                  We use as filler text for layouts, non-readability is of great
                  importance but because those who do not know how to pursue
                  pleasure rationally encounter consequences that are extremely
                  painful nor again is there anyone.
                </p>
                <div class="space-y-4 grid grid-cols-1 md:grid-cols-2">
                  <div class="flex items-center gap-3">
                    <svg
                      class="w-6 h-6 text-emerald-400 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    <span class="text-gray-800 text-lg">99% Survey Report</span>
                  </div>
                  <div class="flex items-center gap-3">
                    <svg
                      class="w-6 h-6 text-emerald-400 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    <span class="text-gray-800 text-lg">Trusted by teams</span>
                  </div>
                  <div class="flex items-center gap-3">
                    <svg
                      class="w-6 h-6 text-emerald-400 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    <span class="text-gray-800 text-lg">Self-Service</span>
                  </div>
                </div>
              </div>

              <div
                v-show="currentSlide === 1"
                v-if="currentSlide === 1"
                key="slide-1"
                class="absolute inset-0"
              >
                <h2
                  class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 leading-tight"
                >
                  Discover business Opportunities
                </h2>
                <p class="text-gray-600 text-lg mb-8 leading-relaxed">
                  We use as filler text for layouts, non-readability is of great
                  importance but because those who do not know how to pursue
                  pleasure rationally encounter consequences that are extremely
                  painful nor again is there anyone.
                </p>
                <div class="space-y-4 grid grid-cols-1 md:grid-cols-2">
                  <div class="flex items-center gap-3">
                    <svg
                      class="w-6 h-6 text-emerald-400 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    <span class="text-gray-800 text-lg"
                      >Profile Consultation</span
                    >
                  </div>
                  <div class="flex items-center gap-3">
                    <svg
                      class="w-6 h-6 text-emerald-400 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    <span class="text-gray-800 text-lg">Asset management</span>
                  </div>
                  <div class="flex items-center gap-3">
                    <svg
                      class="w-6 h-6 text-emerald-400 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    <span class="text-gray-800 text-lg"
                      >No-risk business idea</span
                    >
                  </div>
                </div>
              </div>

              <div
                v-show="currentSlide === 2"
                v-if="currentSlide === 2"
                key="slide-2"
                class="absolute inset-0"
              >
                <h2
                  class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 leading-tight"
                >
                  Scale your business faster
                </h2>
                <p class="text-gray-600 text-lg mb-8 leading-relaxed">
                  We use as filler text for layouts, non-readability is of great
                  importance but because those who do not know how to pursue
                  pleasure rationally encounter consequences that are extremely
                  painful nor again is there anyone.
                </p>
                <div class="space-y-4 grid grid-cols-1 md:grid-cols-2">
                  <div class="flex items-center gap-3">
                    <svg
                      class="w-6 h-6 text-emerald-400 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    <span class="text-gray-800 text-lg">Growth analytics</span>
                  </div>
                  <div class="flex items-center gap-3">
                    <svg
                      class="w-6 h-6 text-emerald-400 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    <span class="text-gray-800 text-lg">Expert guidance</span>
                  </div>
                  <div class="flex items-center gap-3">
                    <svg
                      class="w-6 h-6 text-emerald-400 flex-shrink-0"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    <span class="text-gray-800 text-lg">Proven strategies</span>
                  </div>
                </div>
              </div>
            </TransitionGroup>
          </div>
        </div>

        <div class="relative h-[600px]">
          <TransitionGroup name="image-shift">
            <div
              v-if="currentSlide === 0"
              key="images-0"
              class="absolute inset-0 flex gap-4"
            >
              <div class="w-[45%] bg-gray-200 rounded-3xl overflow-hidden">
                <img
                  src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?w=600&h=800&fit=crop"
                  alt="Team member"
                  class="w-full h-full object-cover"
                />
              </div>

              <div class="w-[25%] bg-gray-200 rounded-3xl overflow-hidden">
                <img
                  src="https://images.unsplash.com/photo-1580489944761-15a19d654956?w=300&h=800&fit=crop"
                  alt="Team collaboration"
                  class="w-full h-full object-cover"
                />
              </div>

              <div class="w-[25%] bg-gray-200 rounded-3xl overflow-hidden">
                <img
                  src="https://images.unsplash.com/photo-1600880292203-757bb62b4baf?w=300&h=800&fit=crop"
                  alt="Business professional"
                  class="w-full h-full object-cover"
                />
              </div>
            </div>

            <div
              v-if="currentSlide === 1"
              key="images-1"
              class="absolute inset-0 flex gap-4"
            >
              <div class="w-[25%] bg-gray-200 rounded-3xl overflow-hidden">
                <img
                  src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?w=300&h=800&fit=crop"
                  alt="Team member"
                  class="w-full h-full object-cover"
                />
              </div>

              <div class="w-[45%] bg-gray-200 rounded-3xl overflow-hidden">
                <img
                  src="https://images.unsplash.com/photo-1580489944761-15a19d654956?w=600&h=800&fit=crop"
                  alt="Team collaboration"
                  class="w-full h-full object-cover"
                />
              </div>

              <div class="w-[25%] bg-gray-200 rounded-3xl overflow-hidden">
                <img
                  src="https://images.unsplash.com/photo-1600880292203-757bb62b4baf?w=300&h=800&fit=crop"
                  alt="Business professional"
                  class="w-full h-full object-cover"
                />
              </div>
            </div>

            <div
              v-if="currentSlide === 2"
              key="images-2"
              class="absolute inset-0 flex gap-4"
            >
              <div class="w-[25%] bg-gray-200 rounded-3xl overflow-hidden">
                <img
                  src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?w=300&h=800&fit=crop"
                  alt="Team member"
                  class="w-full h-full object-cover"
                />
              </div>

              <div class="w-[25%] bg-gray-200 rounded-3xl overflow-hidden">
                <img
                  src="https://images.unsplash.com/photo-1580489944761-15a19d654956?w=300&h=800&fit=crop"
                  alt="Team collaboration"
                  class="w-full h-full object-cover"
                />
              </div>

              <div class="w-[45%] bg-gray-200 rounded-3xl overflow-hidden">
                <img
                  src="https://images.unsplash.com/photo-1600880292203-757bb62b4baf?w=600&h=800&fit=crop"
                  alt="Business professional"
                  class="w-full h-full object-cover"
                />
              </div>
            </div>
          </TransitionGroup>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const currentSlide = ref(0);
const totalSlides = 3;

let intervalId: NodeJS.Timeout | null = null;

const startAutoPlay = () => {
  intervalId = setInterval(() => {
    currentSlide.value = (currentSlide.value + 1) % totalSlides;
  }, 5000);
};

const stopAutoPlay = () => {
  if (intervalId) {
    clearInterval(intervalId);
  }
};

const goToSlide = (index: number) => {
  currentSlide.value = index;
  stopAutoPlay();
  startAutoPlay();
};

onMounted(() => {
  startAutoPlay();
});

onBeforeUnmount(() => {
  stopAutoPlay();
});
</script>

<style scoped>
.slide-fade-enter-active {
  transition: all 0.6s ease;
}

.slide-fade-leave-active {
  transition: all 0.6s ease;
}

.slide-fade-enter-from {
  transform: translateX(30px);
  opacity: 0;
}

.slide-fade-leave-to {
  transform: translateX(-30px);
  opacity: 0;
}

.image-shift-enter-active {
  transition: all 0.8s ease;
}

.image-shift-leave-active {
  transition: all 0.8s ease;
}

.image-shift-enter-from {
  opacity: 0;
  transform: scale(0.95);
}

.image-shift-leave-to {
  opacity: 0;
  transform: scale(0.95);
}
</style>