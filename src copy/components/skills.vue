<!-- <template>
    <div class="py-24 px-6 text-center bg-transparent">
      <h2 class="text-3xl font-semibold text-white mb-12">Tech Stack</h2>
  
      <div
        class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-6 gap-8 justify-items-center text-white mb-12"
      >
        <div
          v-for="skill in skills"
          :key="skill.name"
          class="flex flex-col items-center space-y-2 hover:scale-105 transition"
        >
          <img
            :src="getIconUrl(skill.icon)"
            :alt="skill.name + ' icon'"
            class="w-12 h-12 object-contain"
          />
          <span class="text-sm">{{ skill.name }}</span>
        </div>
      </div>
  
      <h2 class="text-xl font-semibold text-indigo-400 mb-4 tracking-wider">Other Skills</h2>
      <div class="flex flex-wrap gap-2 justify-center text-sm">
        <span
          v-for="skill in otherSkills"
          :key="skill"
          class="bg-slate-800 rounded-full py-1 px-3 text-white"
          >{{ skill }}</span
        >
      </div>
    </div>
  </template>

  
  <script setup>
  import { ref } from 'vue';
  
  const skills = [
    { name: "Go", icon: "go" },
    { name: "Java", icon: "java" },
    { name: "HTML", icon: "html5" },
    { name: "CSS", icon: "css3" },
    { name: "Vue.js", icon: "vuejs" },
    { name: "Python", icon: "python" },
    { name: "JavaScript", icon: "javascript" },
    { name: "Docker", icon: "docker" },
    { name: "MySQL", icon: "mysql" },
    { name: "SQLite", icon: "sqlite" },
    { name: "Google Cloud", icon: "googlecloud" },
    { name: "Linux", icon: "linux" }, 
    { name: "Git", icon: "git"},
    { name: "GitHub", icon:"github" },
    { name: "TailwindCSS", icon: "tailwindcss"},
    {name: "AWS", icon:"AWS"}
  ];
  
  const otherSkills = ref([
    'REST APIs',
    'Websockets',
    'Network Programming',
    'OWASP TOP 10',
    'JWT Authentication',
  ]);
  
  // Construct icon URL from Devicon CDN
  const getIconUrl = (icon) =>
    `https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/${icon}/${icon}-original.svg`;
  </script> -->



  <template>
  <div class="py-24 px-6 text-center bg-transparent">
    <h2 class="text-3xl font-semibold text-white mb-12">Tech Stack</h2>

    <div
      class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-6 gap-8 justify-items-center text-white mb-12"
    >
      <div
        v-for="skill in skills"
        :key="skill.name"
        class="flex flex-col items-center space-y-2 hover:scale-105 transition"
      >
        <img
          v-if="skill.icon === 'amazonwebservices'"
          src="https://upload.wikimedia.org/wikipedia/commons/9/93/Amazon_Web_Services_Logo.svg"
          :alt="skill.name + ' icon'"
          class="w-12 h-12 object-contain"
        />
        <img
          v-else
          :src="getIconUrl(skill.icon)"
          :alt="skill.name + ' icon'"
          class="w-12 h-12 object-contain"
        />
        <span class="text-sm">{{ skill.name }}</span>
      </div>
    </div>

    <h2 class="text-xl font-semibold text-indigo-400 mb-4 tracking-wider">Other Skills</h2>
    <div class="flex flex-wrap gap-2 justify-center text-sm">
      <span
        v-for="skill in otherSkills"
        :key="skill"
        class="bg-slate-800 rounded-full py-1 px-3 text-white"
        >{{ skill }}</span
      >
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";


const skills = [
  { name: "Go", icon: "go" },
  { name: "Java", icon: "java" },
  { name: "HTML", icon: "html5" },
  { name: "CSS", icon: "css3" },
  { name: "Vue.js", icon: "vuejs" },
  { name: "Python", icon: "python" },
  { name: "JavaScript", icon: "javascript" },
  { name: "Docker", icon: "docker" },
  { name: "MySQL", icon: "mysql" },
  { name: "SQLite", icon: "sqlite" },
  { name: "Google Cloud", icon: "googlecloud" },
  { name: "Linux", icon: "linux" },
  { name: "Git", icon: "git" },
  { name: "GitHub", icon: "github" },
  { name: "TailwindCSS", icon: "tailwindcss" },

];

const otherSkills = ref([
  "REST APIs",
  "Websockets",
  "Network Programming",
  "OWASP TOP 10",
  "JWT Authentication",
]);

const getIconUrl = (icon) =>
  `https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/${icon}/${icon}-original.svg`;
</script>
