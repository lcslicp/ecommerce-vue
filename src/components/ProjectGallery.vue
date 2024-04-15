<template>
    <section class="project-section flex-col">
        <h2><span class="subheadline">Projects</span> <br />
        <span class="section-headline">{{ sectionTitle }}</span></h2>
        <div class="gallery-container">
            <div v-for="(image, index) in imagesSetOne" :key="index" class="gallery-item">
                <img :src="requireImage(image.src)" :alt="image.alt">
                <div class="gallery-label">
                    <h4>{{ image.projectTitle }}</h4>
                    <button class="btn-link">Learn More <svg width="4" height="11" viewBox="0 0 20 32" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M0 28.24L12.2133 16L0 3.76L3.76 0L19.76 16L3.76 32L0 28.24Z" fill="white"/></svg></button>
                </div>
                <div class="overlay"></div>
            </div>
        </div>

        <div class="gallery-container-two">
            <div v-for="(image, index) in imagesSetTwo" :key="index" class="gallery-item">
                <img :src="requireImage(image.src)" :key="image.alt" class="">
                <div class="gallery-label">
                    <h4>{{ image.projectTitle }}</h4>
                    <button class="btn-link">Learn More <svg width="4" height="11" viewBox="0 0 20 32" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M0 28.24L12.2133 16L0 3.76L3.76 0L19.76 16L3.76 32L0 28.24Z" fill="white"/></svg></button>
                </div>
                <div class="overlay"></div>
            </div>
        </div>
    </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

interface Gallery {
    src: string,
    alt: string,
    projectTitle: string
}

export default defineComponent({
    props: {
        sectionTitle: {
            type: String,
            required: true,
        },
        imagesSetOne: {
            type: Array as () => Gallery[],
            required: true
        },
        imagesSetTwo: {
            type: Array as () => Gallery[],
            required: true
        }
    },
    setup(props) {
        const requireImage = (src:string) => {
            return require(`@/assets${src}`)
        }
        const sectionTitle = props.sectionTitle;
        const imagesSetOne = props.imagesSetOne;
        const imagesSetTwo = props.imagesSetTwo;
        return {
            requireImage,
            sectionTitle,
            imagesSetOne,
            imagesSetTwo
        }
    }
})
</script>

<style scoped>
h2, h4, p, button {
    margin: 0;
}
.project-section {
    justify-content: center;
    align-items: center;
    height: fit-content;
    padding: 6em 0;
}
h2 {
    text-align: center;
    width: 40%;
}
.gallery-container, .gallery-container-two {
    width: 100%;
    height: fit-content;
    display: grid;
    grid-template-rows: 12em 12em;
    gap: 0.5em;
}
.gallery-container {
    grid-template-columns: auto auto 25% 25%;
    grid-template-areas:
    "proj1 proj1 proj2 proj3"
    "proj1 proj1 proj4 proj4";
    padding-bottom: 0.5em;
}
.gallery-container-two {
    grid-template-columns: 25% 25% auto auto;
    grid-template-areas:
    "proj1 proj2 proj3 proj3"
    "proj4 proj4 proj3 proj3";
}
.gallery-container .gallery-item:first-child, .gallery-container-two .gallery-item:first-child {
    grid-area: proj1;
}
.gallery-container .gallery-item:nth-child(2), .gallery-container-two .gallery-item:nth-child(2) {
    grid-area: proj2;
}
.gallery-container .gallery-item:nth-child(3), .gallery-container-two .gallery-item:nth-child(3) {
    grid-area: proj3;
}
.gallery-container .gallery-item:last-child, .gallery-container-two .gallery-item:last-child {
    grid-area: proj4;
}
.gallery-container .gallery-item img, .gallery-container-two .gallery-item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
.gallery-item {
    position: relative;
}
.gallery-label, .overlay {
    position: absolute;
    left: 0;
    bottom: 0;
    visibility: hidden;
}
.gallery-item:hover .gallery-label, .gallery-item:hover .overlay {
    visibility: visible;
}
button {
    padding: 0;
    margin: 0;
}
.gallery-label, button {
    color: var(--white);
    z-index: 9;
}
.gallery-label {
    padding: 0 0 0.8em 1em;
}
h4 {
    padding: 0;
    font-size: 0.9em;
    font-weight: 800;
}
.btn-link {
    font-size: 0.7em;
}
.overlay {
    width: 100%;
    height: 60%;
    background: rgb(0,0,0);
    background: linear-gradient(0deg, rgba(0,0,0,1) 0%, rgba(255,255,255,0) 100%);
    mix-blend-mode: multiply;
}

</style>