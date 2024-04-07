<template>
<footer>
    <div>
        <img :src="imgSrc" :alt="altText">
        <ul>
            <li><h5>Quick Links</h5></li>
            <li>Home</li>
            <li>About Us</li>
            <li>Services</li>
            <li>Testimonials</li>
            <li>Contact Us</li>
        </ul>

        <ul>
            <li><h5>Other</h5></li>
            <li>Terms of Service</li>
            <li>Cookie Policy</li>
            <li>Privacy Policy</li>
        </ul>
    </div>
    <div>
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
        const imgSrc = props.imgSrc;
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