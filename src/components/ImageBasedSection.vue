<template>
    <section class="imgSection flex-row">
        <div>
            <h2 class="section-headline">{{ sectionTitle }}</h2>
            <button class="btn-light">Learn More</button>
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