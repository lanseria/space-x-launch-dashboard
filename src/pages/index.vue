<script setup lang="ts">
</script>

<template>
  <div class="w-full h-full relative overflow-hidden">
    <div class="absolute h-1920px w-1920px bottom--1757px">
      <div class="h-1920px w-1920px rounded-1/2 bg-gradient-to-r absolute from-transparent via-dark-500 to-transparent opacity-20 border-3px text-white" />
      <svg width="1920" height="1920">
        <defs>
          <linearGradient id="grad" x1="0%" y1="0%" x2="100%" y2="0%">
            <stop offset="0%" stop-color="transparent" />
            <stop offset="40%" stop-color="rgba(0, 0, 0, 0.1)" />
            <stop offset="60%" stop-color="rgba(0, 0, 0, 0.1)" />
            <stop offset="100%" stop-color="transparent" />
          </linearGradient>
        </defs>
        <defs>
          <linearGradient id="grad1" x1="0%" y1="0%" x2="100%" y2="0%">
            <stop offset="0%" stop-color="transparent" />
            <stop offset="40%" stop-color="rgba(0, 0, 0, 0.2)" />
            <stop offset="60%" stop-color="rgba(0, 0, 0, 0.2)" />
            <stop offset="100%" stop-color="transparent" />
          </linearGradient>
        </defs>
        <circle cx="960" cy="960" r="960" fill="url(#grad)" stroke="rgba(255, 255, 255, 0.5)" stroke-width="3" />
        <circle cx="960" cy="960" r="910" fill="url(#grad1)" stroke="rgba(255, 255, 255, 0.8)" stroke-width="2" />
      </svg>
    </div>
  </div>
</template>
