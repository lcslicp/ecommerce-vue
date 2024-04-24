<template>
    <section class="hero-section">
        <h1>
            <span class="subheadline">{{ subheadline }}</span> <br />
            <span class="headline">{{ sectionTitle }}</span>
        </h1>
        <p>{{ sectionText }}</p>
        <button class="btn-light">Learn More <svg width="5" height="12" viewBox="0 0 20 32" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M0 28.24L12.2133 16L0 3.76L3.76 0L19.76 16L3.76 32L0 28.24Z" fill="#181317"/></svg></button>
        
        <div class="hero-bg flex-row">
            <div v-for="(image, index) in images" :key="index" class="bg-item">
                <img :src="requireImage(image.src)" :alt="image.alt">
            </div>
        </div>
        
    </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

interface HeroBackground {
    src: string,
    alt: string,
}

export default defineComponent({
    props: {
        images: {
            type: Array as () => HeroBackground[],
            required: true,
        },
        subheadline: {
            type: String,
            required: true
        },
        sectionTitle: {
            type: String,
            required: true
        },
        sectionText: {
            type: String,
            required: true
        }
    },
    setup(props) {
        const requireImage = (src:string) => {
            return require(`@/assets${src}`);
        }
        const subheadline = props.subheadline;
        const sectionTitle = props.sectionTitle;
        const sectionText = props.sectionText;

        return {
            requireImage,
            images: props.images,
            subheadline,
            sectionTitle,
            sectionText
        }
    }
})
</script>

<style scoped>
.hero-section {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
    row-gap: 0.8em;
}
.hero-bg {
    position: absolute;
    top: 0%;
    right: 0;
    width: 60%;
    opacity: 0.5;
    filter: brightness(0.7);
    z-index: 0;
}
.bg-item {
  width: 35%;
  max-height: 95vh;
}
.bg-item img {
    width: 100%;
    height: 95vh;
    object-fit: cover;
}
h1 {
    margin: 0;
    padding-bottom: 0.3em;
}
.hero-section > p {
  width: 60%;
  margin: 0;
  padding-bottom: 1.2em;
}
h1, p, button {
    z-index: 3;
}
h1 {
    width: 80%;
 } 
.headline {
  font-size: 2.2em;
}

/* portrait tablets, large phones  */
@media screen and (min-width: 600px) {
    .hero-bg {
        width: 70%;
    }
    .headline {
        font-size: 3em;
    }
}

/* landscape tablets */
@media screen and (min-width: 768px) {
    h1 {
        width: 70%;
    }
    .hero-bg {
        width: 65%;
    }  
    .hero-section > p {
        width: 45%;
        padding-bottom: 1.3em;
    }
}

/* laptops and desktops */
@media screen and (min-width: 992px) {
    .hero-bg {
        width: 65%;
    } 
    h1 {
        width: 45%;
    } 
    .headline {
        font-size: 3em;
    }
    .hero-section > p {
        width: 30%;
    }
}

/* large screens */
@media screen and (min-width: 1200px) {
    .hero-bg {
        width: 70%;
    }
    h1 {
        width: 45%;
    }
    .hero-section > p {
        width: 20%;
        padding-bottom: 1.8em;
    } 

}

</style>