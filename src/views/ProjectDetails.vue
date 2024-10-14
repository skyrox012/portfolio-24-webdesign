<template>
  <div>
    <!-- Navbar en haut de la page -->
    <Navbar />

    

    <!-- Contenu principal du projet -->
    <div class="project-details">

        <!-- Flèche de retour en haut à gauche -->
        <div class="back-arrow">
            <router-link to="/projects" class="btn btn-outline-primary">
            <i class="bi bi-arrow-90deg-left"></i> Retour aux projets
            </router-link>
        </div>

      <h1>{{ project.title }}</h1>
      <p>{{ project.description }}</p>

      <h3>Compétences utilisées</h3>
      <ul>
        <li v-for="skill in project.skills" :key="skill">{{ skill }}</li>
      </ul>

      <a :href="project.link" target="_blank" class="btn btn-primary">Voir le projet en ligne</a>

      <h3>Images du projet</h3>
      <div class="row">
        <div class="col-md-4" v-for="image in project.images" :key="image">
          <img :src="image" alt="Project Image" class="img-fluid mb-3" />
        </div>
      </div>
    </div>

    <!-- Footer en bas de la page -->
    <Footer />
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue';
import { useRoute } from 'vue-router';
import Navbar from '@/components/Navbar.vue';  // Importer le composant Navbar
import Footer from '@/components/Footer.vue';

// Fonction pour charger les images depuis le dossier assets
function getImageUrl(imageName) {
  return new URL(`../assets/${imageName}`, import.meta.url).href;
}

const projects = [
  {
    id: 1,
    title: 'Site web - Mon école digitale',
    description: "Dans le cadre de mon évaluation en Approche développement frontend, j'ai conçu un site web interactif pour des instituteurs et élèves de primaire. Le site vise à offrir aux élèves un espace pédagogique en ligne, comprenant des exercices de mathématiques, de français et d'éveil, classés par niveau et thème. Le projet inclut également l'intégration de vidéos éducatives.",
    skills: ['HTML', 'CSS', 'JavaScript', 'Bootstrap'],
    images: [
      getImageUrl('ExamJavascript_(1).png'),  // Référence à une image dans assets
      getImageUrl('ExamJavascript_.png'),      
    ],
    link: 'https://juliedeschoenmaekers.be/ExamJavascript/'
  },
  // D'autres projets ici
  {
    id: 2,
    title: 'Site responsive en HTML/CSS',
    description: "Dans le cadre d'une évaluation scolaire, j'ai développé une application web statique basée sur un contenu fictif. Le projet consistait à créer un site web en HTML et CSS, respectant les normes W3C ainsi que la séparation entre le contenu et le style. Le site devait être compatible avec les navigateurs modernes et responsive pour différents appareils (smartphones, tablettes, ordinateurs).",
    skills: ['HTML', 'CSS'],
    images: [
      getImageUrl('ExamHTMLCSS-2024_(1).png'),  // Référence à une image dans assets
      getImageUrl('ExamHTMLCSS-2024_.png'), 
      getImageUrl('ExamHTMLCSS-2024_(3).png'),      
    ],
    link: 'https://juliedeschoenmaekers.be/ExamHTMLCSS-2024/'
  },
  {
    id: 3,
    title: 'Site Web Wordpress - Inductance',
    description: "Ce projet avait pour objectif de concevoir et de publier un site web dynamique pour la société Inductance en utilisant WordPress comme CMS, conformément aux exigences du cahier des charges fourni par le client. Le projet incluait le choix et la personnalisation d'un Template, l'intégration de plugins adaptés, la mise en ligne du site ainsi que la mise en place d'une procédure de maintenance pour garantir la sécurité et les sauvegardes régulières.",
    skills: ['Wordpress'],
    images: [
      getImageUrl('ExamCMS.png'),  // Référence à une image dans assets
      getImageUrl('ExamCMS_peb-particuliers.png'),      
      getImageUrl('ExamCMS_contact.png'),
    ],
    link: 'https://www.juliedeschoenmaekers.be/ExamCMS/'
  },
  {
    id: 4,
    title: 'Brandboard + Maquette + logo - "3x20"',
    description: "Dans le cadre d'un examen de design UI, j'ai réalisé l'identité visuelle complète ainsi que la maquette d'un site web pour 3x20, une boutique en ligne spécialisée dans les vêtements pour hommes et femmes de plus de 60 ans, avec un focus sur les grandes tailles. Le projet incluait la création d'un Brandboard, d'un logo déclinable, ainsi que la conception de l'interface utilisateur du site web en respectant les attentes du client.",
    skills: ['Photoshop', 'Illustrator', 'Adobe XD'],
    images: [
      getImageUrl('BrandBoard-3x20.png'),  // Référence à une image dans assets
      getImageUrl('Maquette-desktop-3x20.png'),   
      getImageUrl('Maquette-mobile-3x20.png'),      
      getImageUrl('Menu-mobile-3x20.png'),   
    ],
    link: 'https://xd.adobe.com/view/6fe6aa16-942c-43d1-895e-02061658981d-3ab5/?fullscreen'
  },
  {
    id: 5,
    title: 'Brandboard + Maquette - Rocca A Mare',
    description: "Dans le cadre de mon examen de design UX, j'ai réalisé la maquette d'un site web pour Rocca A Mare, une ancienne bergerie située en Corse et transformée en gîte. Ce site est destiné à promouvoir la location de ce logement unique, perdu en pleine nature, offrant une immersion totale dans la culture corse. Le projet incluait la création d'une identité visuelle, la maquette du site, et un cahier des charges détaillé ainsi qu'un devis. En collaboration avec Maurine MEEUS et Sara SAMBREE.",
    skills: ['Photoshop', 'Illustrator', 'Adobe XD'],
    images: [
      getImageUrl('BrandBoard_RocaAMare.png'),  // Référence à une image dans assets
      getImageUrl('RoccaAMare-Desktop.png'),   
      getImageUrl('RoccaAMare-Mobile.png'),      
      getImageUrl('Rocca-Menu-mobile.png'),   
    ],
    link: '#'
  },
  {
    id: 6,
    title: 'Brandboard + Maquette - Saveur Des Thés',
    description: "Dans le cadre d'un exercice de Design UI, j'ai réalisé un Brandboard et une maquette One Page pour Saveurs des thés, une marque belge de thés et tisanes 100% naturels et bio. Ce projet a été conçu en utilisant une approche mobile-first, assurant une expérience utilisateur optimale sur tous les appareils.",
    skills: ['Photoshop', 'Adobe XD'],
    images: [
      getImageUrl('BrandBoard_SaveursDesThes.png'),  // Référence à une image dans assets
      getImageUrl('Maquette-SaveurDesThes-desktop.png'),  
      getImageUrl('Maquette-SaveurDesThes-mobile.png'),  
      getImageUrl('SaveurDesThes-menu-mobile.png'),      
    ],
    link: '#'
  },
  {
    id: 7,
    title: 'Infographie -  ASBL Tout Un Village',
    description: "Dans le cadre de mon examen de Design UI vectoriel, j'ai conçu une infographie illustrant le processus d'accompagnement de l'ASBL Tout un Village. Cette infographie est destinée aux bénévoles et candidats bénévoles, appelés coéquipiers et coéquipières. L'objectif est de fournir un support concret et informatif qui les aidera à réfléchir à leur choix de devenir bénévoles.",
    skills: ['Adobe Express', ' Illustrator', 'Rebelle 5'],
    images: [
      getImageUrl('infographie ToutUnVillage.png'),  // Référence à une image dans assets
           
    ],
    link: '#'
  },
  {
    id: 8,
    title: 'Logo - Ferme du Vallon',
    description: "Dans le cadre d’un exercice de Design UI, j’ai réalisé un logo pour la Ferme du Vallon, une entreprise familiale active depuis 40 ans, pionnière en Wallonie dans la vente de légumes frais et locaux. L’objectif était de concevoir une identité graphique qui reflète l’histoire, les valeurs et la mission de la ferme tout en attirant un large public.",
    skills: ['Illustrator', 'Photoshop'],
    images: [
      getImageUrl('logo2@2x.png'),  // Référence à une image dans assets
      getImageUrl('45.jpg'),   
      getImageUrl('Billboard_Mockup-fdv.jpg'),   
      getImageUrl('Free Hand Holding iPhone 13 Mockup PSD.jpg'),  
      getImageUrl('Free Lunch Kraft Paper Bag Mockup.jpg'),  
      getImageUrl('mockup-cap.jpg'),   
      getImageUrl('Mockup-PoloShirt.jpg'),  
 
    
    ],
    link: '#'
  },
  {
    id: 9,
    title: 'Jeu icones - Aéromodélisme',
    description: "Dans le cadre d'un exercice de Design UI, j'ai conçu un ensemble de cinq icônes destinées à un site web dédié à un sujet au choix (ici, à l'aéromodélisme). Ces icônes ont pour objectif d'améliorer l'expérience utilisateur en facilitant la navigation et en apportant une dimension visuelle attrayante au site.",
    skills: ['Illustrator', 'Adobe XD'],
    images: [
      getImageUrl('Les-icones-aeromodelisme.png'),  // Référence à une image dans assets
           
    ],
    link: '#'
  },
  {
    id: 10,
    title: 'Autres réalisations',
    description: "J'ai rassemblé ici d'autres réalisations, comme des exercices d'apprentissage des logiciels Adobe et des projets personnels.",
    skills: ['Photoshop', 'Illustrator', 'PaintTool Sai', 'Rebelle 5'],
    images: [
      getImageUrl('Autres/2karusa redraw2.jpg'),
      getImageUrl('Autres/banniere web_marche-noel.png'),
      getImageUrl('Autres/Coloriage-Photoshop.jpg'),
      getImageUrl('Autres/ettiquette-confiture.png'),
      getImageUrl('Autres/Ex-pinceau-illustrator.png'),
      getImageUrl('Autres/Illustration-formes-jusfruit.png'),
      getImageUrl('Autres/Karu-losing-it-cover.jpg'),
      getImageUrl('Autres/Karu-losing-it.jpg'),
      getImageUrl('Autres/Karus02.png'),
      getImageUrl('Autres/Karus03.png'),
      getImageUrl('Autres/LesAsperges.png'),
      getImageUrl('Autres/Mario and Luigi.jpg'),
      getImageUrl('Autres/MIAM.png'),
      getImageUrl('Autres/Origami-etoile.jpg'),
      getImageUrl('Autres/Peluche-Pathfinder.png'),
      getImageUrl('Autres/pp.jpg'),
      getImageUrl('Autres/Projet-creatif-atelier.png'),
      getImageUrl('Autres/Projet-PastaDeliziosa.png'),
      getImageUrl('Autres/Saiki kusuo 3.jpg'),
      getImageUrl('Autres/Sans 3.jpg'),
      getImageUrl('Autres/SansAquarelle.jpg'),
      getImageUrl('Autres/SensiMegot.png'),
      getImageUrl('Autres/sketch 2 dr.strange v3.jpg'),
      getImageUrl('Autres/sketch 2 Joe D..jpg'),
      getImageUrl('Autres/sketch bob4.jpg'),
      getImageUrl('Autres/splatoon chara human.png'),
      getImageUrl('Autres/Splatoon.png'),
      getImageUrl('Autres/Zootopio.png'),
     
    ],
    link: 'https://juliedeschoenmaekers.be/ExamJavascript/'
  },
];

const route = useRoute();
const project = ref({});

onMounted(() => {
  const projectId = route.params.id;
  project.value = projects.find(p => p.id === parseInt(projectId));
});
</script>

<style scoped>
.project-details {
  color:#95deff;
  background-image: url("@/assets/fond-accueil.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;
  padding:30px;
}

h1, h3 {
  color: #fa1593;
}

ul {
  list-style-type: none;
  padding: 0;
}

ul li {
  margin-bottom: 10px;
}

img {
  
  padding: 5px;
  
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
