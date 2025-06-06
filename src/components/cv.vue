<template>
    <div class="p-8 text-gray-300 font-sans">
      <section class="mb-10">
        <h2 class="text-xl font-semibold text-indigo-400 mb-3 tracking-wider">WORK EXPERIENCE</h2>
        <hr class="border-t border-gray-700 mb-6">
        <div v-for="(experience, index) in experiences" :key="index" class="mb-8">
          <h3 class="font-semibold text-white text-lg">{{ experience.title }}</h3>
          <p class="text-sm text-indigo-300 font-medium">{{ experience.company }} <span class="text-gray-400">|</span> {{ experience.location }}</p>
          <p class="text-sm text-gray-400 mt-1">{{ experience.startDate }} – {{ experience.endDate }}</p>
          <p class="mt-2 text-sm text-gray-300 leading-relaxed">{{ experience.description.join(' ') }}</p>
        </div>
      </section>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const experiences = ref([
    {
      title: 'Software Developer Intern',
      company: 'Pente Guard',
      location: 'Remote',
      startDate: 'Jan 2025',
      endDate: 'Now',
      description: [
        'Developed real-time WebSocket services in Go and Python to stream live network data (Zeek, TCPDump) into the company\'s AI threat detection engine.',
        'Built a secure Java Spring Boot backend for the SODEFEND project (SOC Bootcamp portal) with JWT authentication, Spring Security, and hardened database interactions using JPA/Hibernate for MySQL.',
        'Implemented security best practices to protect against SQL Injection, XSS, and Broken Authentication vulnerabilities.',
        'Upgraded legacy desktop AI monitoring tools into secure web-based interfaces using HTML, CSS, JavaScript, and Python WebSockets.',
      ],
    },
  ]);
  </script>