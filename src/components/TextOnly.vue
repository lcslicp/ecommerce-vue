<template>
    <div class="flex-row container">
        <h2><span class="subheadline">{{ subheadline }}</span><br/>
        <span class="section-headline">{{ sectionTitle }}</span>
        </h2>
        <p>{{ sectionText }}</p>
    </div>

</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    props: {
        subheadline: {
            type: String,
            required: true,
        },
        sectionTitle: {
            type: String,
            required: true,
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

<style scoped>
h2 {
    min-width: 40%;
}
p {
    margin: 0;
    height: 100%;
}

.container {
    align-items: center;
    gap: 5em;
}
</style>