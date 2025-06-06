   <template>
    <div class="min-h-screen w-full bg-gradient-to-br from-slate-950 via-gray-900 to-slate-800 text-white relative overflow-hidden">
  

      <div class="absolute inset-0 pointer-events-none z-0">
        <div class="bg-dots opacity-5 w-full h-full"></div>
      </div>
  

      <div v-for="i in 6" :key="'circle'+i" class="floating-circle absolute rounded-full bg-white opacity-10 blur-md z-0"
        :style="generateCircleStyle(i)">
      </div>
  

      <div v-for="i in 8" :key="'line'+i" class="falling-line absolute w-px bg-white opacity-10 z-0"
        :style="generateLineStyle(i)">
      </div>
  

      <div class="relative z-10 px-6 py-10 max-w-7xl mx-auto">
        <slot />
      </div>
    </div>
  </template>
  
  <script setup>
  const generateCircleStyle = (i) => {
    const top = Math.random() * 100 + '%'
    const left = Math.random() * 100 + '%'
    const size = 40 + Math.random() * 40
    const duration = 10 + Math.random() * 10
    return {
      top,
      left,
      width: `${size}px`,
      height: `${size}px`,
      animation: `float ${duration}s ease-in-out infinite`,
    }
  }
  
  const generateLineStyle = (i) => {
    const left = Math.random() * 100 + '%'
    const height = 40 + Math.random() * 60
    const duration = 4 + Math.random() * 4
    const delay = Math.random() * 5
    return {
      top: '-100px',
      left,
      height: `${height}px`,
      animation: `fall ${duration}s linear ${delay}s infinite`,
    }
  }
  </script>
  
  <style scoped>
  @keyframes float {
    0%, 100% {
      transform: translateY(0px);
    }
    50% {
      transform: translateY(-30px);
    }
  }
  
  @keyframes fall {
    0% {
      transform: translateY(-100%);
      opacity: 0;
    }
    50% {
      opacity: 0.2;
    }
    100% {
      transform: translateY(120vh);
      opacity: 0;
    }
  }
  </style>
  
