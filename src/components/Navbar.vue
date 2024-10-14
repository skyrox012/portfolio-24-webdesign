<template>
  <nav class="navbar navbar-expand-lg">
    <div class="container">
      <a class="navbar-brand" href="/"><img src="/monlogo.png" alt="logo Julie Deschoenmaekers" width="50px">Julie D. - Portfolio</a>
      <button
        class="navbar-toggler"
        type="button"
        @click="toggleNavbar"
        aria-controls="navbarNav"
        aria-expanded="isOpen"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
        <span v-if="isOpen" class="navbar-toggler-close" aria-hidden="true">
          <i class="bi bi-x"></i>
        </span>
        <span v-else class="navbar-toggler-open" aria-hidden="true">
          <i class="bi bi-list"></i>
        </span>
      </button>

      <div class="collapse navbar-collapse" :class="{ show: isOpen }" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <router-link class="nav-link" to="/">Accueil</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/projects">Mes Projets</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/about">À propos</router-link>
          </li>
          
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue';

const isOpen = ref(false);

const toggleNavbar = () => {
  isOpen.value = !isOpen.value;
};
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

.navbar{
  background-color: #004b6b;
  color:#95deff;
  font-family : Montserrat;
  z-index: 15;
}

.navbar-toggler {
  border: none; /* Enlève le contour */
}

.navbar-toggler-icon {
  background-image: none; /* Supprime l'image par défaut */
}

.navbar-toggler-close {
  font-size: 2rem; /* Taille de l'icône de fermeture */
  color:#95deff;
  
}

.navbar-toggler-open {
  font-size: 2rem; /* Taille de l'icône de menu hamburger */
  color:#95deff;
  
}

/* Optionnel : si tu veux également enlever les ombres ou styles au focus */
.navbar-toggler:focus {
  box-shadow: none; /* Enlève l'ombre au focus */
}

.nav-link{
  text-align: right;
  color:#95deff;
  
}

.nav-link:hover, .nav-link:focus{
  color:#fa1593;
}

.navbar-brand{
  color:#95deff;
  display: flex;
  align-items: center;
  font-family : planer;
  font-size: 1.5em;
  column-gap: 5px;
}

.navbar-brand:hover, .navbar-brand:focus{
 color: #fa1593;
}



</style>

