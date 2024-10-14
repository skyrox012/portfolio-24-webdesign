<template>
  <footer class="text-center text-lg-start">
    <div class="container p-4">
      <div class="row">
        <div class="col-lg-6 col-md-12 mb-4">
          <h5 class="text-uppercase">Mon Portfolio</h5>
          <p>
            Merci d'avoir visité mon portfolio. N'hésitez pas à me contacter pour toute demande ou question.
          </p>
        </div>
      </div>
    </div>

    <div class="text-center p-3">
      &copy; {{ new Date().getFullYear() }} Portfolio - Julie D. - Tous droits réservés.
    </div>
  </footer>
</template>

<script setup>
// Aucune logique spécifique
</script>

<style scoped>
@font-face {
    font-family : Montserrat;
    src: url(/fonts/planer/Montserrat-VariableFont_wght.ttf);
}

footer {
  font-family : Montserrat;
  position: relative;
  bottom: 0;
  width: 100%;
  background-color:#004b6b;
  color:#95deff;
}
</style>
