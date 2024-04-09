<template>
    <section class="project-section">
        <h2><span class="subheadline">Projects</span> <br />
        <span class="section-headline">{{ sectionTitle }}</span></h2>
        <div>
            <div v-for="(image, index) in imagesSetOne" :key="index">
                <img :src="image.src" :alt="image.alt">
                <div>
                    <h4>{{ image.projectTitle }}</h4>
                    <button>Learn More</button>
                </div>
            </div>
            <div v-for="(image, index) in imagesSetTwo" :key="index">
                <img :src="image.src" :key="image.alt">
                <div>
                    <h4>{{ image.projectTitle }}</h4>
                    <button>Learn More</button>
                </div>
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
        const sectionTitle = props.sectionTitle;
        const imagesSetOne = props.imagesSetOne;
        const imagesSetTwo = props.imagesSetTwo;
        return {
            sectionTitle,
            imagesSetOne,
            imagesSetTwo
        }
    }
})
</script>