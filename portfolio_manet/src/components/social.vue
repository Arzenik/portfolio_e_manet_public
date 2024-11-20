<template>
  <div class="social">
    <div class="social_img">
      <a v-for="(link, index) in links" :key="index" :href="link.url">
        <img :src="link.icon" :alt="link.alt" />
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "Social",
  props: ["links"],
};
</script>

<style scoped>
.social {
  display: flex; /* Utilise Flexbox */
  justify-content: center; /* Aligne les icônes horizontalement au centre */
  align-items: center; /* Centre les icônes verticalement */
  gap: 15px; /* Ajoute de l'espacement entre les icônes */
  padding: 10px; /* Optionnel : ajoute un peu d'espace autour */
}

.social a {
  display: inline-block; /* Chaque icône reste un bloc cliquable */
}

.social img {
  width: 50px; /* Ajuste la taille des icônes */
  height: 50px;
  transition: transform 0.3s ease; /* Ajoute une animation au survol */
}

.social img:hover {
  transform: scale(1.1); /* Agrandit légèrement l'icône au survol */
}
</style>
