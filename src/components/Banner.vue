<template>
  <header class="banner">
    <div class="banner-content">
      <img src="/monlogo.png" alt="logo Julie Deschoenmaekers" width="200px">
      <h1>Bienvenue sur mon Portfolio</h1>
      <p>
        Découvrez mes projets et compétences en web design.
      </p>
      <router-link to="/projects" class="btn btn-primary btn-lg">Voir mes projets <i class="bi bi-folder2-open"></i></router-link>
    </div>
    <img src="@/assets/fond-accueil.png" alt="Header Image" class="banner-image" />
  </header>
</template>

<script setup>
// Vous pouvez ajouter ici des scripts si nécessaire
</script>

<style scoped>
@font-face {
    font-family : planer;
    src: url(/fonts/planer/Planer-Regular.ttf);
}

.banner {
  
  text-align: center;
  color: #95deff; /* Couleur du texte pour qu'il soit lisible sur l'image */
  font-family : planer;
  width: 200vh;
  height: auto;
}

.banner-content {
  position: absolute; /* Positionnement absolu pour centrer le contenu */
  top: 50%; /* Centre verticalement */
  left: 50%; /* Centre horizontalement */
  transform: translate(-50%, -50%); /* Ajuste pour centrer parfaitement */
  z-index: 10; /* Assure que le texte est au-dessus de l'image */
  
  
  
  
}

.banner h1 {
  font-size: 2.5rem; /* Taille du titre */
  margin-bottom: 10px; /* Espacement en bas du titre */
}

.banner p {
  font-size: 1.2rem; /* Taille du texte de la description */
  margin-bottom: 20px; /* Espacement en bas de la description */
}

.banner-image {
  max-width: 100%;
  height: auto;
  opacity: 100%; /* Réduit l'opacité de l'image pour faire ressortir le texte */
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
