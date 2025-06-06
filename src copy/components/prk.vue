<template>
  <div class="py-24 px-6 text-gray-300 font-sans">
    <h2 class="text-3xl font-semibold text-white mb-12 text-center tracking-wider">Projects</h2>
    <div class="space-y-12">
      <div v-for="project in projects" :key="project.name" class="bg-gray-900 bg-opacity-80 rounded-xl shadow-lg overflow-hidden md:flex">
        <div class="md:w-1/3 relative">
          <img
            v-if="project.image"
            :src="project.image"
            :alt="project.name"
            class="w-full h-full object-cover rounded-t-xl md:rounded-l-xl md:rounded-tr-none"
          />
          <div v-else class="w-full h-48 bg-gray-800 flex items-center justify-center rounded-t-xl md:rounded-l-xl md:rounded-tr-none">
            <span class="text-gray-500 text-sm italic">Image Placeholder</span>
          </div>
        </div>
        <div class="p-6 md:w-2/3">
          <h3 class="text-xl font-semibold text-indigo-400 mb-2">{{ project.name }}</h3>
          <p class="text-sm text-gray-400 mb-4">{{ project.description }}</p>
          <div class="flex flex-wrap gap-2 mb-4">
            <img
              v-for="tech in project.techStack"
              :key="tech"
              :src="getIconUrl(tech)"
              :alt="tech"
              class="w-8 h-8 object-contain"
              :title="tech"
            />
          </div>
          <a v-if="project.link" :href="project.link" target="_blank" class="text-indigo-300 hover:text-indigo-400 transition text-sm">
            View Project
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const projects = ref([
  {
    name: 'Credit Mortgage',
    description:
      'Imaginary banking platform with user portals for clients, bank employees, and investors. Built with micro-services architecture; each portal has its backend, UI, and database. Currently completing bank employee module.',
    techStack: ['java', 'spring', 'mysql', 'javascript'],
    image: '/src/assets/credit.png',
    link: null,
  },
  {
    name: 'Data Mint & PDF Keyword Extractor',
    description:
      'A data visualisation website for Turkish banks, using ChartJS for analysis, and a PDF keyword extraction tool (Apache PDFBox in Java) for financial data search. Containerised with Docker.',
    techStack: ['java', 'docker', 'chartjs'],
    image: '/src/assets/data_mint.png',
    link: null,
  },
  {
    name: 'Mercedes-Benz Guide Project',
    description:
      'Built a full-stack web application to display technical details of Mercedes-Benz cars using Go for the backend, SQLite for the embedded database, and JavaScript, HTML, CSS for the frontend. Developed REST APIs for communication. Containerized with Docker and deployed using Google Cloud Run. Frontend hosted on GitHub Pages.',
    techStack: ['go', 'sqlite', 'javascript', 'html5', 'css3', 'docker', 'googlecloud'],
    image: '/src/assets/mercedes.png',
    link: 'https://alihusseinas.github.io/mercedesBenzGuide/',
  },
  {
    name: 'Diabetes Risk Assessment Website',
    description:
      'A risk assessment tool for Type 2 diabetes using American Diabetes Association guidelines. Developed with Java Spring Boot, Vanilla JS, and MySQL. Containerised with Docker for easy deployment.',
    techStack: ['java', 'spring', 'javascript', 'mysql', 'docker'],
    image: '/src/assets/risk.png',
    link: null,
  },
  {
    name: 'SODEFEND',
    description:
      'Custom-built web platform for monitoring networking activities and managing security-related tickets. The backend was developed using Java Spring with JWT authentication, incorporating OWASP Top 10 security practices to prevent common web vulnerabilities.',
    techStack: ['mysql', 'java', 'spring'],
    image: '/src/assets/sodefend.png',
    link: null,
  },
]);

const getIconUrl = (icon) => {
  return `https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/${icon}/${icon}-original.svg`;
};
</script>