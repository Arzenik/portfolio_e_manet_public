<template>
  <a :href="link" class="button">{{ text }}</a>
</template>

<script>
export default {
  name: "Button",
  props: ["text", "link"],
};
</script>

<style scoped>
.button {
  /* Styles pour le bouton */
  /* Styles pour le bouton */
}
</style>
