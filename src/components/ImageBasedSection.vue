<template>
    <section class="imgSection flex-row">
        <div>
            <h3>{{ sectionTitle }}</h3>
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