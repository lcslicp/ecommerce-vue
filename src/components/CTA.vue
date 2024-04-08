<template>
    <section class="CTA-section flex-col">
        <h2><span>Contact Us</span><br />
{{ sectionTitle }}</h2>

    <form action="" class="flex-col">
        <input type="text" placeholder="Enter Full Name">
        <input type="text" placeholder="Enter E-mail Address">
        <input type="text" placeholder="Enter Message">
        <button type="submit" class="btn-light">Submit</button>
    </form>
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