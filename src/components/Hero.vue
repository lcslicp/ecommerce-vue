<template>
    <section>
        <h1><span>{{ subheadline }}</span>
            {{ sectionTitle }}</h1>
            <p>{{ sectionText }}</p>
            <button>Learn More &#8641;</button>
    </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    props: {
        subheadline: {
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
        }
    },
    setup(props) {
        const subheadline = props.subheadline;
        const sectionTitle = props.sectionTitle;
        const sectionText = props.sectionText;

        return {
            subheadline,
            sectionTitle,
            sectionText
        }
    }
})
</script>