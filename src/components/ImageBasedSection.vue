<template>
    <section class="img-container">
        <div class="img-section flex-row">
            <div>
            <h2 class="section-headline">{{ sectionTitle }}</h2>
            <button class="btn-light">Learn More <svg width="5" height="12" viewBox="0 0 20 32" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M0 28.24L12.2133 16L0 3.76L3.76 0L19.76 16L3.76 32L0 28.24Z" fill="#181317"/></svg></button>
            </div>
        
            <p>{{ sectionText }}</p>
        </div>
    </section>
   
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent ({
    props: {
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
        const sectionTitle = props.sectionTitle;
        const sectionText = props.sectionText;

        return {
            sectionTitle,
            sectionText
        }
    }
})
</script>

<style scoped>
.img-container {
    background-image: url('/src/assets/service-img-04.jpeg');
    background-size: cover;
    background-position: center center;
    background-repeat: no-repeat;
    background-color: rgba(24,19, 23, 0.7);
    background-blend-mode: multiply;
    color: var(--white);
    padding: 6em 0;
    position: relative;
}
.img-section {
    justify-content: space-between;
    align-items: center;
    gap: 8em;
}
.img-section > div {
    width: 50%;
}
</style>