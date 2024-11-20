<template>
  <div class="cover">
    <img :src="src" :alt="alt" class="img-fluid w-100" />
  </div>
</template>

<script>
export default {
  name: "Cover",
  props: {
    src: {
      type: String,
      required: true, // L'URL de l'image est obligatoire
    },
    alt: {
      type: String,
      default: "Image de couverture", // Texte alternatif par défaut
    },
  },
};
</script>

<style scoped>
.cover {
  max-height: 100vh; /* Facultatif : limite la hauteur si nécessaire */
}
</style>
