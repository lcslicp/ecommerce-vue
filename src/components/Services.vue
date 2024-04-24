<template>
    <section class="services-section container flex-col">
        <h2><span class="subheadline">Services</span> <br />
        <span class="section-headline"><span>Elevating spaces</span> with comprehensive wall finishings</span>
        </h2>

        <div class="flex-row service-container">
            <div v-for="(image, index ) in images" :key="index" class="flex-col service-item">
            <img :src="requireImage(image.src)" :alt="image.alt">
            <button class="btn-biege flex-row">{{ image.btnText }} 
                <svg width="5" height="12" viewBox="0 0 20 32" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M0 28.24L12.2133 16L0 3.76L3.76 0L19.76 16L3.76 32L0 28.24Z" fill="#181317"/></svg>
            </button>
            </div>
        </div>
    </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

interface ImageItem {
    src: string;
    alt: string;
    btnText: string;
}

export default defineComponent({
    props: {
        images: {
            type: Array as () => ImageItem[],
            required: true,
        },
    },
    setup(props) {
        const requireImage = (src: string) => {
            return require(`@/assets${src}`);
        }
        return {
            requireImage,
            images: props.images
        }
    }
})

</script>

<style scoped>
.container {
    align-items: center;
    padding: 3em 0 6em 0;
}
h2 {
    text-align: center;
    margin: 0;
    padding-bottom: 1.2em;
}
h2, .service-container, button, .service-item {
    width: 100%;
}
.service-container {
    flex-wrap: wrap;
    justify-content: center;
    gap: 3em;
}
.service-item {
    gap: 1.5em;
}
img {
    height: 30em;
    object-fit: cover;
}

/* portrait tablets, large phones  */
@media screen and (min-width: 600px) {

}

/* landscape tablets */
@media screen and (min-width: 768px) {
    .service-container {
        gap: 2em;
    }
    .service-item {
        gap: 1em;
    }
    .service-item {
        width: 45%;
    }
    img {
    width: 100%;
    height: 30em;
    object-fit: cover;
    }

}

/* laptops and desktops */
@media screen and (min-width: 992px) {
    h2 {
        width: 60%;
    }
    .service-container, .service-item {
        gap: 0.5em;
    }
    .service-container {
        flex-wrap: nowrap;
    }
}

/* large screens */
@media screen and (min-width: 1200px) {
    h2 {
        width: 50%;
    }
    .service-container, .service-item {
        gap: 1em;
    }
  }
</style>