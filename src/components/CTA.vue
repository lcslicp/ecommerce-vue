<template>
    <section class="CTA-container">
        <div class="CTA-section flex-col">
            <h2><span class="subheadline">Contact Us</span><br />
            <span class="section-headline">{{ sectionTitle }}</span></h2>

            <form action="" class="flex-col">
            <input type="text" placeholder="Enter Full Name">
            <input type="text" placeholder="Enter E-mail Address">
            <textarea name="" id="" cols="20" rows="5"placeholder="Enter Message"></textarea>
            <button type="submit" class="btn-light">Submit</button>
            </form>
        </div>

        <div class="CTA-bg flex-row">
            <div v-for="(image, index) in images" :key="index" class="bg-item">
                <img :src="requireImage(image.src)" :alt="image.alt">
            </div>

        </div>
        
    </section>

</template>

<script lang="ts">
import { defineComponent } from 'vue';

interface CTABackground {
    src: string,
    alt: string
}

export default defineComponent({
    props: {
        sectionTitle: {
            type: String,
            required: true
        },
        images: Array as () => CTABackground[]
    },
    setup(props) {
        const sectionTitle = props.sectionTitle;
        const requireImage = (src:string) => {
            return require(`@/assets${src}`)
        }
        return {
            sectionTitle,
            requireImage,
            images: props.images
        }
    }
})
</script>

<style scoped>
.CTA-container {
    background-color: var(--black);
    height: fit-content;
    position: relative;
}
.CTA-section {
    padding: 5em 0;
}
.section-headline {
    color: var(--white);
}
h2, form {
    margin: 0;
    z-index: 9;
}
h2 {
    width: 40%;
}
form {
    width: 30%;
    gap: 0.5em;
}
input, textarea {
    background-color: transparent;
    border: none;
    border-bottom: 0.3px solid var(--gray);
    padding: 1em 0.2em 0.5em 0.4em;
    color: var(--white);
}
button {
    margin-top: 1.5em;
}
.CTA-bg {
    position: absolute;
    top: 0;
    right: 0;
    width: 60%;
    height: 100%;
    opacity: 0.5;
    filter: brightness(0.7);
}
.bg-item {
    width: 35%;
}
.bg-item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
</style>