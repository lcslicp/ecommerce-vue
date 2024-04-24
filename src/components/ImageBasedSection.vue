<template>
    <section class="img-container">
        <div class="img-section">
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
    padding: 5em 0;
    position: relative;
}
.img-section {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 0;
}
.img-section > div {
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    gap: 1em;
}
h2 {
    text-align: left;
    font-size: 1.5em;
}
h2, button {
    width: 50%;
}

/* portrait tablets, large phones  */
@media screen and (min-width: 600px) {

}

/* landscape tablets */
@media screen and (min-width: 768px) {
    .img-section > div {
        width: 100%;
        flex-direction: column;
        align-items: flex-start;
    }
    .img-section {
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        text-align: left;
        gap: 3em;
    }
    h2 {
        width: 120%;
    }
    button {
        width: inherit;
    }
}

/* laptops and desktops */
@media screen and (min-width: 992px) {
    h2 {
        width: 100%;
        font-size: 1.8em;
    }
    .img-section {
        gap: 3em;
    }
    button {
        width: 50%;
    }
}

/* large screens */
@media screen and (min-width: 1200px) {
    .img-section > div {
        gap: 0;
    }
    .img-section {
        gap: 1em;
    }
    h2 {
        font-size: 1.9em;
    }
}
</style>