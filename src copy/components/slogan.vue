<template>
    <div class="relative flex flex-col justify-center items-center mt-32 h-[400px] text-center overflow-hidden">

      <div class="absolute w-full h-full overflow-hidden pointer-events-none z-0">
        <div
          v-for="(dot, index) in visuals"
          :key="index"
          class="absolute rounded-full bg-indigo-300/10 blur-xl animate-floating"
          :style="{
            width: dot.size + 'px',
            height: dot.size + 'px',
            top: dot.top + '%',
            left: dot.left + '%',
            animationDelay: dot.delay + 's'
          }"
        ></div>
      </div>
  

      <p
        class="text-4xl md:text-5xl lg:text-6xl font-semibold tracking-wide bg-gradient-to-r from-indigo-400 via-cyan-300 to-blue-400 text-transparent bg-clip-text drop-shadow-xl z-10 mb-8"
      >
        Engineering Silence Behind<br class="hidden sm:block" />
        Seamless Experiences.
      </p>
    </div> 
  </template>
  
  <script setup>
  const visuals = [
    { size: 100, top: 25, left: 40, delay: 0 },
    { size: 80, top: 55, left: 52, delay: 1 },
    { size: 60, top: 45, left: 35, delay: 2 },
    { size: 90, top: 35, left: 60, delay: 1.5 },
    { size: 70, top: 50, left: 48, delay: 2.5 },
  ];
  </script>
  
  <style scoped>
  @keyframes floating {
    0%, 100% {
      transform: translateY(0px) translateX(0px);
      opacity: 0.15;
    }
    50% {
      transform: translateY(-10px) translateX(5px);
      opacity: 0.3;
    }
  }
  .animate-floating {
    animation: floating 10s ease-in-out infinite;
  }
  </style>
  


