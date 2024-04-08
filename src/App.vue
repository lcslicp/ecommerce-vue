<template>
  <section class="header-section">
    <Header :imgSrc="logo"/>
    <Hero :subheadline="heroSubheadline" :sectionTitle="heroTitle" :sectionText="heroText" />
    <button class="scroll">v</button>
  </section>
  <section class="about-section">
    <ImageCard
    altText="Minimalist living room sofa"
    imgSrc="/minimalist-living.jpeg"
    :imgCardTitle="imgCardTitle"
    :imgCardText="imgCardText" />
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
import IconsSection from './components/IconsSection.vue'
import ImageBasedSection from './components/ImageBasedSection.vue';
import ProjectGallery from './components/ProjectGallery.vue';
import CTA from './components/CTA.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: { Header, Hero, ImageCard, Services, ImageBasedSection, IconsSection, ProjectGallery, CTA, Footer },
  data() {
    return {
      logo: "/logoipsum-logo.svg",
      heroSubheadline: "Transforming Walls",
      heroTitle: "Innovative Wall Finishes",
      heroText: "Elevate your space with our exceptional wall finishings & explore a new dimension of interior design.",
      imgCardTitle: "Nurturing imagination to architectural elegance",
      imgCardText: "Evolving from a shared passion for design excellence, our narrative revolves around the relentless pursuit of crafting extraordinary wall finishes.",

      servicesArray: [
        {
          src: "/minimalist-living.jpeg",
          alt: "service 1",
          btnText: "Textured Wall Installations",
        },
        {
          src: "/minimalist-living.jpeg",
          alt: "service 2",
          btnText: "Artisan Drywall Finishes",
        },
        {
          src: "/minimalist-living.jpeg",
          alt: "service 3",
          btnText: "Custom Mural Creations",
        },
        {
          src: "/minimalist-living.jpeg",
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
          icon: "/icon.svg",
          iconAlt: "Innovative Designs",
          text: "Pioneering creativity, our team delivers avant-garde designs that not only  captivate but redefine the very essence of your space, inspiring awe."
        },
        {
          title: "Quality Craftmanship",
          icon: "/icon.svg",
          iconAlt: "Quality Craftmanship",
          text: "Crafting each finish, we go beyond the surface, ensuring that every detail reflects a commitment to creating an immersive experience."
        },
        {
          title: "Client-Centric Approach",
          icon: "/icon.svg",
          iconAlt: "Client-Centric Approach",
          text: "Our approach is centered around you. We tailor solutions to your unique vision, engaging in a collaborative process."
        },
        {
          title: "Proven Track Record",
          icon: "/icon.svg",
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
  --borwn: #61544a;
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
h1, h2, h3 {
  font-family: "Lexend Deca", sans-serif;
  font-weight: 600;
}
h4, .subheadline, li, p, button  {
  font-family: "Mulish", sans-serif;
}
p {
  font-size: 0.8em;
  line-height: 1.5em;
}
h1 {
  width: 40%;
}
li {
  list-style: none;
}
a {
  text-decoration: none;
}
header, .footer-upper, .scroll {
  margin: 0 auto;
}
header, .footer-upper {
  max-width: 1440px;
  width: 90%;
}
.hero-section, .about-section, .services-section, .icon-section, .imgSection, .project-section, .CTA-section {
  width: 75%;
  margin: auto;
  border: 1px solid blue;
}
.btn-light {
  background-color: var(--white);
}
.btn-dark {
  background-color: var(--black);
  color: var(--white);
}
.btn-beige {
  background-color: var(--biege);
}
button {
  border: none;
  padding: 0.7em 2em;
}
.flex-col, .flex-row {
  display: flex;
}
.flex-col {
  flex-direction: column;
}
.flex-row {
  flex-direction: row;
}
.header-section {
  display: flex;
  flex-direction: column;
  background-color: var(--black);
  min-height: 95vh;
  color: var(--white);
  justify-content: center;
  /* justify-content: space-around; */
  align-items: flex-start;
  align-content: space-around;
  border: 1px solid blue;
}
.subheadline {
  text-transform: uppercase;
  font-weight: 700;
  color: var(--gray);
  font-size: 0.8em;
}
.headline {
  font-size: 3em;
}
.scroll {
  align-self: flex-start;
}

</style>
