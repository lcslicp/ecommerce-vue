<template>
    <section class="imgSection flex-row">
        <div>
            <h2 class="section-headline">{{ sectionTitle }}</h2>
            <button class="btn-light">Learn More <svg width="5" height="12" viewBox="0 0 20 32" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M0 28.24L12.2133 16L0 3.76L3.76 0L19.76 16L3.76 32L0 28.24Z" fill="#181317"/></svg></button>
        </div>
        
        <p>{{ sectionText }}</p>

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