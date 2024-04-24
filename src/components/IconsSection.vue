<template>
    <section class="icon-section">
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
        text-align: center;
    }
    .main-text, button {
        width: 100%;
    }
    .main-text {
        padding-bottom: 2em;
    }
    h2, h3 {
        padding-bottom: 0.5em;
    }
    p {
        padding-bottom: 1em;
    }
    .icon-section {
        display: flex;
        flex-direction: column;
    }
    .icon-items {
        display: flex;
        flex-direction: column;
        color: var(--white);
        background-color: var(--black);
        padding: 5em 3em;
        margin-right: -2em;
        margin-left: -2em;
    }
    .icon-item {
        align-items: flex-start;
        gap: 1em;
    }
    img {
        margin-top: 0.1em;
    }

    /* portrait tablets, large phones  */
@media screen and (min-width: 600px) {

}

/* landscape tablets */
@media screen and (min-width: 768px) {
    p {
        padding-bottom: 1.5em;
    }
    .icon-items {
        padding: 6em 25%;
        margin-right: -25%;
        margin-left: -25%;
    }
}

/* laptops and desktops */
@media screen and (min-width: 992px) {
    .main-text {
        width: 60%;
        padding-right: 2em;
        text-align: left;
    }
    .icon-section {
        flex-direction: row;
        flex-wrap: nowrap;
        align-items: center;
    }
    .icon-items {
        padding: 6em 25% 6em 6em;
    }
    .icon-items:nth-child(-n + 2) {
        grid-area: first-two;
    }
    .icon-items:nth-last-child(-n + 2) {
        grid-area: last-two;
    }
    .icon-items:nth-child(-n + 2) {
        grid-area: first-two;
    }
    .icon-items:nth-last-child(-n + 2) {
        grid-area: last-two;
    }
    .icon-items {
        display: grid;
        grid-template-columns: 40% 40%;
        grid-template-rows: auto;
        grid-template-areas: 
        "first-two"
        "last-two";
        gap: 2em;
        padding: 5em 6em 5em 3em;
        margin-right: -25%;
        margin-left: 0;
    }
    .icon-item {
        align-items: flex-start;
        gap: 1em;
    }
}

/* large screens */
@media screen and (min-width: 1200px) {
    .icon-items {
        grid-template-columns: 45% 45%;
        padding: 7em 25% 7em 7em;
    }
    .main-text {
        width: 70%;
        padding-right: 5em;
        text-align: left;
    }
  }

</style>