<template>
  <div class="app">
    <div class="container-fluid">
      <div class="row">
        <!-- Colonne pour Social -->
        <div class="col-md-3 d-flex">
          <Logo />
          <Menu />
          <Social :links="socialLinks" />
        </div>

        <!-- Colonne pour Cover -->
        <div class="col-md-9">
          <Cover
            src="https://www.grandpalais.fr/sites/default/files/user_images/144/jeune-public/JP-HA-Manet-14-526263.jpg"
            alt="Ma belle image"
          />
        </div>
      </div>
    </div>

    <section class="container text-center">
      <div class="row">
        <div class="col">
          <Card
            title="A propos"
            subtitle="Le Japon comme terrain d'art"
            text="Peintre, dessinateur spécialiste de lukiyo-e..."
            link="#"
            image="https://www.grandpalais.fr/sites/default/files/user_images/144/jeune-public/JP-HA-Manet-14-526263.jpg"
            :main="true"
          />
        </div>
        <div class="col">
          <Quatuor :images="quatuorImages" />
        </div>
      </div>
    </section>

    <section>
      <h2>Mon Blog</h2>
      <Card
        v-for="(post, index) in blogPosts"
        :key="index"
        :title="post.title"
        :subtitle="post.subtitle"
        :image="post.image"
        :link="post.link"
      />
    </section>
  </div>
</template>

<script>
import Logo from "./components/Logo.vue";
import Menu from "./components/Menu.vue";
import Social from "./components/Social.vue";
import Card from "./components/Card.vue";
import Quatuor from "./components/Quatuor.vue";
import Cover from "./components/Cover.vue";

export default {
  name: "App",
  components: { Logo, Menu, Social, Cover, Card, Quatuor },
  data() {
    return {
      socialLinks: [
        {
          icon: "https://cdn-icons-png.flaticon.com/512/124/124021.png",
          url: "#",
          alt: "Twitter",
        },
        {
          icon: "https://cdn-icons-png.flaticon.com/512/174/174863.png",
          url: "#",
          alt: "Pinterest",
        },
        {
          icon: "https://cdn-icons-png.flaticon.com/512/174/174857.png",
          url: "#",
          alt: "LinkedIn",
        },
      ],
      quatuorImages: [
        "https://www.museumtv.art/wp-content/uploads/2021/05/7CC3BF82-C9EC-4B42-8830-050D1CC0E69A-485x600.jpeg",
        "https://www.museumtv.art/wp-content/uploads/2021/05/7CC3BF82-C9EC-4B42-8830-050D1CC0E69A-485x600.jpeg",
        "https://www.museumtv.art/wp-content/uploads/2021/05/7CC3BF82-C9EC-4B42-8830-050D1CC0E69A-485x600.jpeg",
        "https://www.museumtv.art/wp-content/uploads/2021/05/7CC3BF82-C9EC-4B42-8830-050D1CC0E69A-485x600.jpeg",
      ],
      imageUrls: [],
      blogPosts: [
        {
          title: "Salle Horizon à Muret",
          subtitle: "Les 12 et 15 octobre 2024...",
          image:
            "https://cdn.finestresullarte.info/rivista/immagini/2022/fn/edouard-manet.jpg",
          link: "#",
        },
        // Ajouter d'autres posts de blog ici
      ],
    };
  },
};
</script>

<style scoped src="./assets/styles/tailwind.css">
.coversite {
  display: flex; /* Social et Cover côte à côte */
  align-items: center; /* Alignement vertical au centre */
  gap: 15px; /* Espacement entre Social et Cover */
  width: 100%; /* Prend toute la largeur disponible */
}
</style>
