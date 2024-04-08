<template>
    <section class="icon-section flex-row">
        <div>
            <h2><span class="subheadline">{{ subheadline }}</span> <br />
        {{ sectionTitle }}</h2>
        <p>{{ sectionText }}</p>
        <button class="btn-dark">Learn More</button>
        </div>
        <div v-for="(item, index) in items" :key="index">
            <h3>{{ item.title }}</h3>
            <img :src="item.icon" :alt="item.iconAlt">
            <p>{{ item.text }}</p>
        </div>
    </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

interface iconItem {
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
            type: Array as () => iconItem[],
            required: true
        }
    }
})
</script>