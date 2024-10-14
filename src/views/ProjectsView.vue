<template>
  <div>
    <Navbar />
   
    <div class="projects-list">
      <ProjectCard v-for="project in projects" :key="project.id" :project="project" />
    </div>
    <Footer />
  </div>
  
</template>

<script setup>
import { ref } from 'vue';
import Navbar from '@/components/Navbar.vue';
import Footer from '@/components/Footer.vue';
import ProjectCard from '@/components/ProjectCard.vue';

const projects = ref([
  {
    id: 1,
    title: 'Mon école digitale',
    description: 'Site web - JS/HTML/CSS',
    image: '/juliedeschoenmaekers.be_ExamJavascript-minia.png',
    link: 'https://xd.adobe.com/view/6fe6aa16-942c-43d1-895e-02061658981d-3ab5/?fullscreen'
  },
  // Ajoutez d'autres projets ici
  {
    id: 2,
    title: 'Responsive design',
    description: 'Site - HTML/CSS',
    image: '/juliedeschoenmaekers.be_ExamHTMLCSS-2024-minia.png',
    link: 'https://xd.adobe.com/view/6fe6aa16-942c-43d1-895e-02061658981d-3ab5/?fullscreen'
  },
  {
    id: 3,
    title: 'Inductance',
    description: 'Site - Wordpress',
    image: '/www.juliedeschoenmaekers.be_ExamCMS-minia.png',
    link: 'https://xd.adobe.com/view/6fe6aa16-942c-43d1-895e-02061658981d-3ab5/?fullscreen'
  },
  {
    id: 4,
    title: '3X20',
    description: 'Logo, Brandboard et maquette',
    image: '/Maquette-desktop-3x20-minia.png',
    link: 'https://xd.adobe.com/view/6fe6aa16-942c-43d1-895e-02061658981d-3ab5/?fullscreen'
  },
  {
    id: 5,
    title: 'Rocca A Mare',
    description: 'Brandboard et Maquette',
    image: '/Rocca A Mare - Desktop-minia.png',
    link: 'https://xd.adobe.com/view/6fe6aa16-942c-43d1-895e-02061658981d-3ab5/?fullscreen'
  },
  // Ajoutez d'autres projets ici
  {
    id: 6,
    title: 'Saveur Des Thés',
    description: 'Brandboard et Maquette',
    image: '/SaveurDesThes-minia.png',
    link: 'https://xd.adobe.com/view/6fe6aa16-942c-43d1-895e-02061658981d-3ab5/?fullscreen'
  },
  {
    id: 7,
    title: 'ASBL - Tout Un Village',
    description: 'Infographie',
    image: '/infographie ToutUnVillage-minia.png',
    link: 'https://xd.adobe.com/view/6fe6aa16-942c-43d1-895e-02061658981d-3ab5/?fullscreen'
  },
  {
    id: 8,
    title: 'Ferme Du Vallon',
    description: 'Logo',
    image: '/logoFermeDuVallon@2x-minia.png',
    link: 'https://xd.adobe.com/view/6fe6aa16-942c-43d1-895e-02061658981d-3ab5/?fullscreen'
  },
  {
    id: 9,
    title: 'Aéromodélisme',
    description: 'Icones',
    image: '/Icones-aeromodelisme-minia.png',
    link: 'https://xd.adobe.com/view/6fe6aa16-942c-43d1-895e-02061658981d-3ab5/?fullscreen'
  },
  {
    id: 10,
    title: 'Autres réalisations',
    description: 'Photoshop/Illustrator/autres',
    image: '/Autres-réalisations-minia.png',
    link: 'https://xd.adobe.com/view/6fe6aa16-942c-43d1-895e-02061658981d-3ab5/?fullscreen'
  },
]);
</script>

<style scoped>
.projects-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  background-image: url("@/assets/fond-accueil.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;
}
</style>
