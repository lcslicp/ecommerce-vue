<template>
  <section class="hero-section">
    <Header />
    <Hero />
  </section>
  <section class="about-section">
    <ImageCard
    altText="Minimalist living room sofa"
    imgSrc="/minimalist-living.jpeg"
    :imgCardTitle="imgCardTitle"
    :imgCardText="imgCardText" />
  </section>
  
</template>

<script lang="ts">
import Header from './components/Header.vue';
import Hero from './components/Hero.vue'
import ImageCard from './components/ImageCard.vue';

export default {
  name: 'App',
  components: { Header, Hero, ImageCard },
  data() {
    return {
      imgCardTitle: "Nurturing imagination to architectural elegance",
      imgCardText: "Evolving from a shared passion for design excellence, our narrative revolves around the relentless pursuit of crafting extraordinary wall finishes."
    }
  }

}
</script>

<style>

h1 {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  color: #2c3e50;
  margin-top: 60px;
}

/* headings: lexend deca
body: mulish */
</style>
