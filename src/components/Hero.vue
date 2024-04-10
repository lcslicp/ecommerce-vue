<template>
    <section class="hero-section">
        <h1>
            <span class="subheadline">{{ subheadline }}</span> <br />
            <span class="headline">{{ sectionTitle }}</span>
        </h1>
        <p>{{ sectionText }}</p>
        <button class="btn-light">Learn More <svg width="5" height="12" viewBox="0 0 20 32" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M0 28.24L12.2133 16L0 3.76L3.76 0L19.76 16L3.76 32L0 28.24Z" fill="#181317"/></svg></button>
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

<style scoped>
.hero-section {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
    row-gap: 0.8em;
}
h1 {
    margin: 0;
}

.hero-section > p {
  width: 26%;
}

</style>