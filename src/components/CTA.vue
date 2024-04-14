<template>
    <section class="CTA-container flex-col">
        <div class="CTA-section">
            <h2><span class="subheadline">Contact Us</span><br />
            <span class="section-headline">{{ sectionTitle }}</span></h2>

            <form action="" class="flex-col">
            <input type="text" placeholder="Enter Full Name">
            <input type="text" placeholder="Enter E-mail Address">
            <textarea name="" id="" cols="20" rows="5"placeholder="Enter Message"></textarea>
            <button type="submit" class="btn-light">Submit</button>
            </form>
        </div>
        
    </section>

</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    props: {
        sectionTitle: {
            type: String,
            required: true
        }
    },
    setup(props) {
        const sectionTitle = props.sectionTitle;
        return {
            sectionTitle
        }
    }
})
</script>

<style scoped>
.CTA-container {
    background-color: var(--black);
}
.CTA-section {
    padding: 5em 0;
}
.section-headline {
    color: var(--white);
}
h2, form {
    margin: 0;
}
h2 {
    width: 40%;
}
form {
    width: 30%;
    gap: 0.5em;
}
input, textarea {
    background-color: transparent;
    border: none;
    border-bottom: 0.3px solid var(--gray);
    padding: 1em 0.2em 0.5em 0.4em;
    color: var(--white);
}
button {
    margin-top: 1.5em;
}
</style>