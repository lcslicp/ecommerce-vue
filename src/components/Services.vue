<template>
    <section class="services-section container flex-col">
        <h2><span class="subheadline">Services</span> <br />
        <span class="section-headline"><span>Elevating spaces</span> with comprehensive wall finishings</span>
        </h2>

        <div class="flex-row service-container">
            <div v-for="(image, index ) in images" :key="index" class="flex-col service-item">
            <img :src="requireImage(image.src)" :alt="image.alt">
            <button class="btn-beige">{{ image.btnText }}  &#8641;</button>
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
}
h2 {
    text-align: center;
    width: 60%;
    margin: 0;
}
.service-container, .service-item {
    gap: 1.2em;
    width: 100%;
}
.service-item {
    align-items: center;
}
img, button {
    width: 100%;
}
img {
    height: 30em;
    object-fit: cover;
}
</style>