<template>
  <!-- Desktop Navigation -->
  <nav class="hidden md:flex fixed top-8 left-0 right-0 z-50 px-8 items-center justify-between">
    <!-- Logo  -->
    <NuxtLink to="/" class="flex items-center gap-2">
      <div class="w-10 h-10 bg-gradient-to-br from-blue-400 via-cyan-400 to-purple-400 rounded-lg flex items-center justify-center">
        <svg class="w-6 h-6 text-white" fill="currentColor" viewBox="0 0 24 24">
          <path d="M13 10V3L4 14h7v7l9-11h-7z"/>
        </svg>
      </div>
      <span class="text-2xl font-bold text-white">Staco</span>
    </NuxtLink>

    <!-- Tabs  -->
    <div class="bg-white/10 border border-2 backdrop-blur-md rounded-full p-1 shadow-2xl border border-white/20">
      <div class="flex items-center gap-1 relative bg-gray-500/50 rounded-full p-1">
        <div
          class="absolute bg-white rounded-full transition-all duration-300 ease-out"
          :style="{
            left: `${indicatorLeft + 4}px`,
            width: `${indicatorWidth - 8}px`,
            top: '4px',
            height: 'calc(100% - 8px)'
          }"
        />
        
        <!-- Tab Buttons -->
        <NuxtLink
          v-for="(tab, index) in tabs"
          :key="tab.name"
          :to="tab.path"
          ref="tabRefs"
          @click="selectTab(index)"
          :class="[
            'relative px-6 py-3 text-sm font-medium rounded-full transition-all duration-300 z-10',
            activeTab === index
              ? 'text-gray-900 bg-gray-300 border border-white border-2 m-1'
              : 'text-gray-300 hover:bg-gray-700'
          ]"
        >
          {{ tab.name }}
        </NuxtLink>
      </div>
    </div>

    <div class="w-32"></div>
  </nav>

  <!-- Mobile Navigation -->
  <nav class="md:hidden fixed top-0 left-0 right-0 z-50 bg-gray-900/95 backdrop-blur-lg border-b border-gray-800">
    <div class="flex justify-between items-center px-6 py-4">
      <!-- Logo -->
      <NuxtLink to="/" class="flex items-center gap-2">
        <div class="w-8 h-8 bg-gradient-to-br from-blue-400 via-cyan-400 to-purple-400 rounded-lg flex items-center justify-center">
          <svg class="w-5 h-5 text-white" fill="currentColor" viewBox="0 0 24 24">
            <path d="M13 10V3L4 14h7v7l9-11h-7z"/>
          </svg>
        </div>
        <span class="text-xl font-bold text-white">Staco</span>
      </NuxtLink>

      <!-- Hamburger Menu Button -->
      <button 
        @click="toggleMobileMenu"
        class="w-10 h-10 flex items-center justify-center text-white rounded-lg hover:bg-gray-800 transition-colors"
        aria-label="Toggle menu"
      >
        <svg 
          v-if="!isMobileMenuOpen" 
          class="w-6 h-6" 
          fill="none" 
          stroke="currentColor" 
          viewBox="0 0 24 24"
        >
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
        </svg>
        <svg 
          v-else 
          class="w-6 h-6" 
          fill="none" 
          stroke="currentColor" 
          viewBox="0 0 24 24"
        >
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
        </svg>
      </button>
    </div>

    <!-- Mobile Menu Dropdown -->
    <Transition
      enter-active-class="transition-all duration-300 ease-out"
      enter-from-class="opacity-0 max-h-0"
      enter-to-class="opacity-100 max-h-96"
      leave-active-class="transition-all duration-200 ease-in"
      leave-from-class="opacity-100 max-h-96"
      leave-to-class="opacity-0 max-h-0"
    >
      <div 
        v-if="isMobileMenuOpen" 
        class="overflow-hidden bg-gray-900/95 border-t border-gray-800"
      >
        <div class="px-4 py-4 space-y-2">
          <NuxtLink
            v-for="(tab, index) in tabs"
            :key="tab.name"
            :to="tab.path"
            @click="selectMobileTab(index)"
            :class="[
              'w-full text-left px-4 py-3 rounded-lg font-medium transition-all duration-200 block',
              activeTab === index
                ? 'bg-emerald-400 text-gray-900'
                : 'text-gray-300 hover:bg-gray-800 hover:text-white'
            ]"
          >
            {{ tab.name }}
          </NuxtLink>
        </div>
      </div>
    </Transition>
  </nav>
</template>

<script setup lang="ts">
const route = useRoute()

const tabs = [
  { name: 'Home', path: '/' },
  { name: 'Pages', path: '/pages' },
  { name: 'Services', path: '/services' },
  { name: 'Blogs', path: '/blogs' },
  { name: 'Contact Us', path: '/contact' }
]

const activeTab = ref(0)
const tabRefs = ref<HTMLElement[]>([])
const indicatorLeft = ref(0)
const indicatorWidth = ref(0)
const isMobileMenuOpen = ref(false)

// Watch route changes to update active tab
watch(() => route.path, (newPath) => {
  const index = tabs.findIndex(tab => tab.path === newPath)
  if (index !== -1) {
    activeTab.value = index
    nextTick(() => {
      updateIndicator()
    })
  }
}, { immediate: true })

const updateIndicator = () => {
  if (tabRefs.value[activeTab.value]) {
    const activeElement = tabRefs.value[activeTab.value]
    indicatorLeft.value = activeElement.offsetLeft
    indicatorWidth.value = activeElement.offsetWidth
  }
}

const selectTab = (index: number) => {
  activeTab.value = index
  updateIndicator()
}

const selectMobileTab = (index: number) => {
  activeTab.value = index
  isMobileMenuOpen.value = false
}

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

onMounted(() => {
  nextTick(() => {
    updateIndicator()
  })
  window.addEventListener('resize', updateIndicator)
})

onBeforeUnmount(() => {
  window.removeEventListener('resize', updateIndicator)
})
</script>

<style scoped>
/* Ensure smooth transitions */
</style>