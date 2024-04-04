<template>
    <div>
        <img :src="imgSrc" :alt="altText">
        <div>
            <h3>{{ imgCardTitle }}</h3>
            <p>{{ imgCardText }}</p>
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
        imgCardText: {
            type: String,
            required: true
        }
    },
    setup(props) {
        const altText = props.altText;
        const imgSrc = require(`@/assets${props.imgSrc}`);
        const imgCardTitle = props.imgCardTitle;
        const imgCardText = props.imgCardText;

        return {
            imgSrc,
            altText,
            imgCardTitle,
            imgCardText
        }
    }
})

</script>

<style scoped>
img {
    width: 50%;
}
</style>

<!-- notes april 3, 2024: fix alt text, study setup(), props, defineComponent and ref -->