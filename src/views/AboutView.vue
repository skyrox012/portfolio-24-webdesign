<template>
  <div>
    <!-- Inclusion de la navigation -->
    <Navbar />

    <!-- Contenu principal de la page À propos -->
    <div class="about-container">
      <div class="row">
        <!-- Section gauche avec la photo et l'introduction -->
        <div class="col-md-4 text-center">
          <!-- Ajoute ici ton image de profil -->
          <img src="/pp.jpg" alt="Julie Deschoenmaekers" width="200px" class="img-fluid rounded-circle mb-3" />
          <h2>Julie Deschoenmaekers</h2>
          <p>22 ans - Court-Saint-Etienne (Belgique)</p>
          <p><strong>Web Design</strong></p>
        </div>

        <!-- Section droite avec plus d'infos -->
        <div class="col-md-8">
          <!-- À propos de moi -->
          <h3>À propos de moi</h3>
          <p>
            Je suis Julie Deschoenmaekers, j'ai 22 ans et suis étudiante en Webdesign à l'Ifosup à Wavre. Me spécialisant au design web et au graphisme, je mets en avant mes réalisations et compétences acquises au cours de ma formation. Avec une maîtrise des bases du HTML, CSS, et en design UI/UX, je suis également en train d'approfondir mes connaissances en WordPress.
          </p>

          <!-- Compétences -->
          <h3>Compétences</h3>
          <ul>
            <li><strong>Illustrator :</strong> Créer des logos et icônes</li>
            <li><strong>Photoshop :</strong> Retoucher des images et réaliser des montages graphiques</li>
            <li><strong>Adobe XD :</strong> Faire des maquettes de sites web</li>
            <li><strong>HTML/CSS :</strong> Réaliser une structure web responsive et design</li>
            <li><strong>WordPress :</strong> Créer des sites web sur base d'un CMS</li>
            <li><strong>PaintTool SAI/Rebelle 5 :</strong> Créer des illustrations digitales sur tablette graphique</li>
          </ul>

          <!-- Éducation -->
          <h3>Éducation</h3>
          <ul>
            <li>Collège des Hayeffes - Secondaire (2014-2020)</li>
            <li>Infographie - Haute école Albert Jacquard (2020-2021)</li>
            <li>Web Design - Institut de Formation Supérieure (Wavre) (2023 - 2ème année en cours)</li>
          </ul>

          <!-- Langues -->
          <h3>Langues</h3>
          <ul>
            <li>Français : Langue maternelle</li>
            <li>Anglais : B1</li>
          </ul>

          <!-- Loisirs -->
          <h3>Loisirs</h3>
          <ul>
            <li>Dessin digital</li>
            <li>Jeux vidéo</li>
          </ul>

          <!-- Contact -->
          <h3>Contact</h3>
          <p>
            <strong>Email :</strong> julie.deschoenmaekers@gmail.com<br />
            <strong>Téléphone :</strong> +32 476 92 92 86<br />
            
          </p>
        </div>
      </div>
    </div>

    <!-- Inclusion du pied de page -->
    <Footer />
  </div>
</template>

<script setup>
// Importation des composants Navbar et Footer
import Navbar from '@/components/Navbar.vue';
import Footer from '@/components/Footer.vue';
</script>

<style scoped>
@font-face {
    font-family : Montserrat;
    src: url(/fonts/planer/Montserrat-VariableFont_wght.ttf);
}

.about-container {

  font-family : Montserrat;
  color: #95deff;
  background-image: url("@/assets/fond-accueil.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;

}

h2, h3, ul, p, img{
    margin:30px;

}

h2, h3 {
  color: #fa1593; /* Couleur principale similaire à Bootstrap */
}

ul {
  list-style-type: none;
  padding: 0;
}

ul li {
  margin-bottom: 10px;
}



</style>
