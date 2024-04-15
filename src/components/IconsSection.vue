<template>
    <section class="icon-section flex-row">
        <div class="main-text">
            <h2><span class="subheadline">{{ subheadline }}</span> <br />
        <span class="section-headline">{{ sectionTitle }}</span></h2>
        <p>{{ sectionText }}</p>
        <button class="btn-dark">Learn More <svg width="5" height="12" viewBox="0 0 20 32" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M0 28.24L12.2133 16L0 3.76L3.76 0L19.76 16L3.76 32L0 28.24Z" fill="white"/></svg></button>
        </div>
        <div class="icon-items">
            <div v-for="(item, index) in items" :key="index"  class="flex-row icon-item">
                <img :src="requireImage(item.icon)" :alt="item.iconAlt">
                <div>
                    <h3>{{ item.title }}</h3>
                    <p>{{ item.text }}</p>
                </div>
            
        </div>
        </div>
        
    </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

interface IconItem {
    title: string,
    icon: string,
    iconAlt: string,
    text: string
}

export default defineComponent({
    props: {
        subheadline:{
            type: String,
            required: true
        },
        sectionTitle: {
            type: String,
            required: true
        },
        sectionText: {
            type: String,
            required: true
        },
        items: {
            type: Array as () => IconItem[],
            required: true
        }
    }, setup(props) {
        const subheadline = props.subheadline
        const sectionTitle = props.sectionTitle
        const sectionText = props.sectionText
        const requireImage = (icon: string) => {
            return require(`@/assets${icon}`);
        }
        
        return {
            subheadline,
            sectionTitle,
            sectionText,
            requireImage,
            items: props.items
        }
    }
})
</script>

<style scoped>

    h2, h3, p {
        margin: 0;
    }
    .main-text {
        width: 60%;
        padding-right: 3em;
    }
    h3 {
        padding-bottom: 0.8em;
    }
    p {
        padding-bottom: 2.5em;
    }
    .icon-section {
        align-items: center;
    }
    .icon-items:nth-child(-n + 2) {
        grid-area: first-two;
    }
    .icon-items:nth-last-child(-n + 2) {
        grid-area: last-two;
    }
    .icon-items {
        display: grid;
        grid-template-columns: 45% 45%;
        grid-template-rows: auto;
        grid-template-areas: 
        "first-two"
        "last-two";
        gap: 2em;
        color: var(--white);
        background-color: var(--black);
        padding: 6em 25% 6em 6em;
        margin-right: -25%;
    }
    .icon-item {
        align-items: flex-start;
        gap: 1em;
    }
    img {
        margin-top: 0.1em;
    }

</style>