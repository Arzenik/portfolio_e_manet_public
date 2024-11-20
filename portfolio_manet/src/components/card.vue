<template>
  <div :class="['card', { 'card-horizontal': main }]">
    <div v-if="image" class="card-img">
      <img :src="image" class="img-fluid" alt="Card image" />
    </div>
    <div class="card-body">
      <h5 class="card-title">{{ title }}</h5>
      <h6 v-if="subtitle" class="card-subtitle mb-2 text-muted">{{ subtitle }}</h6>
      <p class="card-text">{{ text }}</p>
      <a :href="link" class="btn btn-primary">Lire la suite</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    title: {
      type: String,
      required: true,
    },
    subtitle: {
      type: String,
      default: "",
    },
    text: {
      type: String,
      required: true,
    },
    link: {
      type: String,
      required: true,
    },
    image: {
      type: String,
      default: "",
    },
    main: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style scoped>
.card {
  display: flex;
  flex-direction: column; /* Par défaut, disposition verticale */
  max-width: 300px; /* Largeur pour disposition verticale */
  margin-bottom: 20px; /* Espacement entre les cartes */
}

.card-horizontal {
  flex-direction: row; /* Disposition horizontale pour la variante main */
  max-width: 600px; /* Largeur plus grande en mode horizontal */
  align-items: center; /* Centrer verticalement */
}

.card-img {
  max-width: 150px;
  margin-bottom: 15px; /* Espacement dans le mode vertical */
}

.card-horizontal .card-img {
  margin-bottom: 0; /* Pas d'espacement en mode horizontal */
  margin-right: 20px; /* Espacement entre l'image et le texte */
}

.card-img img {
  max-width: 100%;
  height: auto;
}

.card-body {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
</style>
