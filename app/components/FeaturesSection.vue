<template>
  <section class="py-24 bg-gray-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
   
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <!-- Feature 1 -->
        <div 
          v-motion
          :initial="{ opacity: 0, y: 50 }"
          :visible="{ opacity: 1, y: 0, transition: { delay: 100 } }"
          class="group bg-white p-8 rounded-3xl shadow-sm hover:shadow-xl transition-all duration-300 relative overflow-hidden"
        >
          <div class="w-16 h-16 bg-emerald-100 rounded-2xl flex items-center justify-center mb-6">
            <svg class="w-8 h-8 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z"/>
            </svg>
          </div>
          <h3 class="text-xl font-bold text-gray-900 mb-4">Bank-Level Security</h3>
          <p class="text-gray-600 mb-8">
            Your data is protected with 256-bit encryption and multi-factor authentication
          </p>
          
          <!-- Learn More Link with Arrow -->
          <a href="#" class="inline-flex items-center gap-2 text-emerald-600 group-hover:text-emerald-700 font-medium">
            <span>Learn more</span>
            <span class="w-10 h-10 bg-gray-100 group-hover:bg-emerald-500 rounded-full flex items-center justify-center transition-all duration-300">
              <svg class="w-5 h-5 text-gray-600 group-hover:text-white group-hover:translate-x-0.5 transition-all duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
              </svg>
            </span>
          </a>
        </div>

        <!-- Feature 2 -->
        <div 
          v-motion
          :initial="{ opacity: 0, y: 50 }"
          :visible="{ opacity: 1, y: 0, transition: { delay: 200 } }"
          class="group bg-white p-8 rounded-3xl shadow-sm hover:shadow-xl transition-all duration-300 relative overflow-hidden"
        >
          <div class="w-16 h-16 bg-emerald-100 rounded-2xl flex items-center justify-center mb-6">
            <svg class="w-8 h-8 text-emerald-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"/>
            </svg>
          </div>
          <h3 class="text-xl font-bold text-gray-900 mb-4">Real-Time Analytics</h3>
          <p class="text-gray-600 mb-8">
            Track your business performance with live dashboards and detailed reports
          </p>
          
          <!-- Learn More Link with Arrow -->
          <a href="#" class="inline-flex items-center gap-2 text-gray-600 group-hover:text-emerald-700 font-medium">
            <span>Learn more</span>
            <span class="w-10 h-10 bg-gray-100 group-hover:bg-emerald-500 rounded-full flex items-center justify-center transition-all duration-300">
              <svg class="w-5 h-5 text-gray-600 group-hover:text-white group-hover:translate-x-0.5 transition-all duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
              </svg>
            </span>
          </a>
        </div>

        <!-- Feature 3 -->
        <div 
          v-motion
          :initial="{ opacity: 0, y: 50 }"
          :visible="{ opacity: 1, y: 0, transition: { delay: 300 } }"
          class="group bg-white p-8 rounded-3xl shadow-sm hover:shadow-xl transition-all duration-300 relative overflow-hidden"
        >
          <div class="w-16 h-16 bg-purple-100 rounded-2xl flex items-center justify-center mb-6">
            <svg class="w-8 h-8 text-purple-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"/>
            </svg>
          </div>
          <h3 class="text-xl font-bold text-gray-900 mb-4">Lightning Fast</h3>
          <p class="text-gray-600 mb-8">
            Process transactions and access your data instantly from anywhere in the world
          </p>
          
          <!-- Learn More Link with Arrow -->
          <a href="#" class="inline-flex items-center gap-2 text-gray-600 group-hover:text-emerald-700 font-medium">
            <span>Learn more</span>
            <span class="w-10 h-10 bg-gray-100 group-hover:bg-emerald-500 rounded-full flex items-center justify-center transition-all duration-300">
              <svg class="w-5 h-5 text-gray-600 group-hover:text-white group-hover:translate-x-0.5 transition-all duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"/>
              </svg>
            </span>
          </a>
        </div>
       
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>