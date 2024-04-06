<template>
    <section>
        <h2><span>Services</span> <br />
        <span>Elevating spaces</span> with comprehensive wall finishings
        </h2>

        <div>
            <div v-for="(image, index ) in images" :key="index">
            <img :src="requireImage(image.src)" :alt="image.alt">
            <button>{{ image.btnText }}  &#8641;</button>
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
img {
    width: 20%;
}
</style>