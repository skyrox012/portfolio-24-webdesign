<template>
  <div class="project-card">
    <img :src="project.image" :alt="project.title" class="card-img-top" />
    <div class="card-body">
      <h3 class="card-title">{{ project.title }}</h3>
      <p class="card-text">{{ project.description }}</p>
      <router-link :to="`/projects/${project.id}`" class="btn btn-primary">Voir le projet</router-link>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';


const props = defineProps({
  project: {
    type: Object,
    required: true
  }
});
</script>

<style scoped>
@font-face {
    font-family : planer;
    src: url(/fonts/planer/Planer-Regular.ttf);
}
@font-face {
    font-family : Montserrat;
    src: url(/fonts/planer/Montserrat-VariableFont_wght.ttf);
}

.project-card {
  border: none; /* Enlève la bordure */
    
  margin: 20px; /* Marge entre les cartes */
  overflow: hidden; /* Évite que le contenu déborde */
  transition: transform 0.2s; /* Transition pour l'effet de survol */
  max-width: 500px; /* Taille maximale de la carte */
  max-height: 610px; /* Taille maximale de la carte */
  text-align: center;
  margin-top: 15px;
  margin-bottom: 15px;
  
  font-family : Montserrat;
}

.project-card:hover {
  transform: scale(1.05); /* Agrandit légèrement la carte au survol */
}

.project-card img {
  max-width: 100%;
  height: auto; /* Assure que l'image garde ses proportions */
  width:90%; /* Taille maximale pour l'image */
  
}

.card-body {
  padding: 15px; /* Ajout d'espace à l'intérieur de la carte */
  color:#95deff;

}
.btn{
  background-color: #004b6b;
  border: none;
  border-radius: 0%;
  color:#95deff;
}

.btn:hover, .btn:focus{
  background-color: #95deff;
  border: none;
  color: #004b6b;
}
</style>
