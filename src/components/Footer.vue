<template>
<footer class="flex-col">
    <div class="footer-upper flex-row">
        <img :src="imgSrc" :alt="altText">
        <ul class="flex-col">
            <li><h5>Quick Links</h5></li>
            <li><a href="">Home</a></li>
            <li><a href="">About Us</a></li>
            <li><a href="">Services</a></li>
            <li><a href="">Testimonials</a></li>
            <li><a href="">Contact Us</a></li>
        </ul>

        <ul class="flex-col">
            <li><h5>Other</h5></li>
            <li><a href="">Terms of Service</a></li>
            <li><a href="">Cookie Policy</a></li>
            <li><a href="">Privacy Policy</a></li>
        </ul>
    </div>
    <div class="footer-lower">
        <p>ArtistryWalls Inc.&copy; {{ currentYear }}</p>
    </div>
</footer>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    props: {
        imgSrc: {
            type: String,
            required: true,
        },
        altText: {
            type: String,
            required: true,
        }
    },
    setup(props) {
        const imgSrc = require(`@/assets${props.imgSrc}`);
        const altText = props.altText;
        const currentYear = new Date().getFullYear();

        return {
            imgSrc,
            altText,
            currentYear
        }
    }
})
</script>

<style scoped>
footer {
    background-color: var(--dark-gray);
    color: var(--white);
}
.footer-upper {
    justify-content: flex-start;
    align-items: flex-start;
    gap: 8em;
    padding: 4em 0;
}
.footer-lower {
    text-align: center;
    text-transform: uppercase;
    border-top: 0.5px solid var(--gray);
}
img {
    width: 25%;
}
h5 {
    text-transform: uppercase;
    font-weight: 700;
}
h5, ul, li {
    margin: 0;
    padding: 0;
}
a {
    color: var(--white);
    font-size: 0.9em;
}
ul {
    gap: 0.4em;
}
</style>