<template>
    <div class="flex-row container">
        <img :src="imgSrc" :alt="altText">
        <div class="text">
            <h3>{{ imgCardTitle }}</h3>
            <p>{{ imgCardText1 }}</p>
            <p>{{ imgCardText2 }}</p>
            <button class="btn-dark">Learn More <svg width="5" height="12" viewBox="0 0 20 32" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M0 28.24L12.2133 16L0 3.76L3.76 0L19.76 16L3.76 32L0 28.24Z" fill="white"/></svg></button>
        </div>
        
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    props: {
        altText: {
            type: String,
            required: true
        },
        imgSrc: {
            type: String,
            required: true
        },
        imgCardTitle: {
            type: String,
            required: true
        },
        imgCardText1: {
            type: String,
            required: true
        },
        imgCardText2: {
            type: String,
            required: true
        }
    },
    setup(props) {
        const altText = props.altText;
        const imgSrc = require(`@/assets${props.imgSrc}`);
        const imgCardTitle = props.imgCardTitle;
        const imgCardText1 = props.imgCardText1;
        const imgCardText2 = props.imgCardText2;

        return {
            imgSrc,
            altText,
            imgCardTitle,
            imgCardText1,
            imgCardText2
        }
    }
})

</script>

<style scoped>
.container {
    background-color: var(--light-gray);
    justify-content: flex-start;
    align-items: center;
    height: 25em;
    gap: 6em;
}
img {
    width: 40%;
    height: inherit;
    object-fit: cover;
}
h3 {
    font-size: 1.4em;
    margin: 0;
}
.text {
    width: 40%;
    height: fit-content;
}
button {
    margin-top: 2.5em;
}
</style>