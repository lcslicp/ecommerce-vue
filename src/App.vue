<template>
  <section class="header-section">
    <Header :imgSrc="logo"/>
    <Hero :subheadline="heroSubheadline" :sectionTitle="heroTitle" :sectionText="heroText" />
    <div class="scroll-div">
      <button class="scroll"><svg width="8" height="8" viewBox="0 0 10 8" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M5 8L0.669873 0.499999L9.33013 0.5L5 8Z"/>
</svg>
</button>
    </div>
  </section>
  <section class="about-section">
    <TextOnly :subheadline="textOnlySubheadline" :sectionTitle="textOnlySectionTitle" :sectionText="textOnlySectionText"/>
    <ImageCard
    altText="Minimalist living room sofa"
    imgSrc="/minimalist-living.jpeg"
    :imgCardTitle="imgCardTitle"
    :imgCardText1="imgCardText1" :imgCardText2="imgCardText2" />
  </section>

  <Services :images="servicesArray" />
  <IconsSection :subheadline="iconSubheadline" :sectionTitle="iconSectionTitle" :sectionText="iconSectionText" :items="iconItems" />
  <ImageBasedSection :sectionTitle="imgSectionTitle" :sectionText="imgSectionText"/>
  <ProjectGallery :sectionTitle="galleryTitle" :imagesSetOne="setOne" :imagesSetTwo="setTwo" />
  <CTA :sectionTitle="CTATitle"/>
  <Footer :imgSrc="logo" :altText="footerAlt" />
  
</template>

<script lang="ts">
import Header from './components/Header.vue';
import Hero from './components/Hero.vue'
import ImageCard from './components/ImageCard.vue';
import Services from './components/Services.vue';
import IconsSection from './components/IconsSection.vue';
import TextOnly from './components/TextOnly.vue';
import ImageBasedSection from './components/ImageBasedSection.vue';
import ProjectGallery from './components/ProjectGallery.vue';
import CTA from './components/CTA.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: { Header, Hero, TextOnly, ImageCard, Services, ImageBasedSection, IconsSection, ProjectGallery, CTA, Footer },
  data() {
    return {
      logo: "/logoipsum-logo.svg",
      heroSubheadline: "Transforming Walls",
      heroTitle: "Innovative Wall Finishes",
      heroText: "Elevate your space with our exceptional wall finishings & explore a new dimension of interior design.",

      textOnlySubheadline: "About Us",
      textOnlySectionTitle: "Crafting Wall Finishings with Mastery",
      textOnlySectionText: "Our commitment to excellence extends beyond the ordinary. With a deep passion for craftsmanship, each stroke and detail contribute to transforming walls into captivating works of art.",

      imgCardTitle: "Nurturing imagination to architectural elegance",
      imgCardText1: "Evolving from a shared passion for design excellence, our narrative revolves around the relentless pursuit of crafting extraordinary wall finishes.",
      imgCardText2: "Our story is a tapestry of creativity, precision, and a commitment to transforming your surroundings into breathtaking masterpieces.",

      servicesArray: [
        {
          src: "/service-img-01.jpeg",
          alt: "service 1",
          btnText: "Textured Wall Installations",
        },
        {
          src: "/service-img-02.jpeg",
          alt: "service 2",
          btnText: "Artisan Drywall Finishes",
        },
        {
          src: "/service-img-03.jpeg",
          alt: "service 3",
          btnText: "Custom Mural Creations",
        },
        {
          src: "/service-img-04.jpeg",
          alt: "service 4",
          btnText: "Plastering Solutions",
        },
      ],

      imgSectionTitle: "Why people should choose ArtistryWalls",
      imgSectionText: "With a commitment to excellence, we pride ourselves on delivering exceptional wall finishing solutions. Our dedicated team ensures a seamless and stress-free experience, making us the ideal choice for transforming your spaces.",

      iconSubheadline: "Unmatched Expertise",
      iconSectionTitle: "Why Us",
      iconSectionText: "Redefine your living and working environments with our unparalleled expertise in wall finishing solutions.",
      iconItems: [
        {
          title: "Innovative Designs",
          icon: "/icon-01.svg",
          iconAlt: "Innovative Designs",
          text: "Pioneering creativity, our team delivers avant-garde designs that not only  captivate but redefine the very essence of your space, inspiring awe."
        },
        {
          title: "Quality Craftmanship",
          icon: "/icon-02.svg",
          iconAlt: "Quality Craftmanship",
          text: "Crafting each finish, we go beyond the surface, ensuring that every detail reflects a commitment to creating an immersive experience."
        },
        {
          title: "Client-Centric Approach",
          icon: "/icon-03.svg",
          iconAlt: "Client-Centric Approach",
          text: "Our approach is centered around you. We tailor solutions to your unique vision, engaging in a collaborative process."
        },
        {
          title: "Proven Track Record",
          icon: "/icon-04.svg",
          iconAlt: "Proven Track Record",
          text: "Building on a legacy of trust, transforming spaces into timeless expressions of sophistication."
        },
      ],
      galleryTitle: "Unveiling Exquisite and Inspiring Wall Creations",
      setOne: [
        {
          src: "/gallery.jpg",
          alt: "alt text",
          projectTitle: "sample title",
        },
        {
          src: "/gallery.jpg",
          alt: "alt text",
          projectTitle: "sample title",
        },
        {
          src: "/gallery.jpg",
          alt: "alt text",
          projectTitle: "sample title",
        }
      ],
      setTwo: [
        {
          src: "/gallery.jpg",
          alt: "alt text",
          projectTitle: "sample title",
        },
        {
          src: "/gallery.jpg",
          alt: "alt text",
          projectTitle: "sample title",
        },
        {
          src: "/gallery.jpg",
          alt: "alt text",
          projectTitle: "sample title",
        }
      ],

      CTATitle: "Begin Your Wall Transformation Journey",
      footerAlt: "Company Logo"
    }
  }

}
</script>

<style>
:root {
  --black: #181317;
  --brown: #61544a;
  --biege: #ddd4cf;
  --dark-gray: #282a2d;
  --gray: #a4a4a2;
  --light-gray: #f3f3f2;
  --white: #ffffff;
}
body {
  width: 100%;
  margin: 0;
  padding: 0;
}

/* for debugging only */
.red {
  border: 1px solid red;
}
.blue {
  border: 1px solid blue;
}
/* for debugging only */

h1, h2, h3 {
  font-family: "Lexend Deca", sans-serif;
  font-weight: 600;
}
h4, .subheadline, li, p, button, input, textarea  {
  font-family: "Mulish", sans-serif;
}
p {
  font-size: 0.8em;
  line-height: 1.5em;
  opacity: 0.7;
}
h1 {
  width: 40%;
}
li {
  list-style: none;
}
a {
  text-decoration: none;
  font-weight: 100;
}
a:hover {
  opacity: 0.5;
  cursor: pointer;
}
header, .footer-upper {
  margin: 0 auto;
}
header {
  width: 90%;
}
header, .footer-upper, .hero-section, .about-section, .services-section, .icon-section, .img-section, .project-section, .CTA-section {
  max-width: 1440px;
}
.hero-section, .about-section, .services-section, .icon-section, .img-section, .project-section, .CTA-section, .footer-upper, .scroll-div {
  width: 75%;
  margin: auto;
}
.about-section {
  padding: 6em 0 3em 0;
}
.btn-light, .scroll:hover {
  background-color: var(--white);
}
.btn-dark {
  background-color: var(--black);
  color: var(--white);
}
.btn-biege {
  background-color: var(--biege);
}
button {
  border: none;
  padding: 0.5em 2em;
  justify-content: center;
  align-items: center;
  gap: 0.5em;
  height: 2.8em;
  cursor: pointer;
}
.btn-light:hover, .scroll, .btn-dark:hover, .btn-biege:hover {
  background-color: transparent;
}
.btn-light:hover, .scroll {
  border: 1px solid var(--white);
  color: var(--white);
}
.btn-light:hover svg path {
  fill: var(--white);
}
.btn-dark:hover {
  border: 1px solid var(--black);
  color: var(--black)
}
.btn-dark:hover svg path {
  fill: var(--black);
}
.btn-biege:hover {
  border: 1px solid var(--brown);
}
.scroll {
  margin: 0;
  border-radius: 50%;
  padding: 0.9em 1.1em;
}
.scroll:hover {
  border: none;
}
.scroll svg path {
  fill: var(--white);
}
.scroll:hover svg path {
  fill: var(--black);
}
.flex-col, .flex-row, button {
  display: flex;
}
.flex-col {
  flex-direction: column;
}
.flex-row, button {
  flex-direction: row;
}
.header-section {
  display: flex;
  flex-direction: column;
  background-color: var(--black);
  min-height: 95vh;
  color: var(--white);
  justify-content: center;
  align-items: flex-start;
  align-content: space-around;
}
.subheadline {
  text-transform: uppercase;
  font-weight: 700;
  color: var(--gray);
  font-size: 15px;
}
.headline {
  font-size: 3em;
}

.section-headline {
  font-size: 1.3em;
}

</style>
