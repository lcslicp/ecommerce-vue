<template>
<footer class="flex-col">
    <div class="footer-upper">
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
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 4em;
    padding: 4em 2em;
}
.footer-lower {
    text-align: center;
    text-transform: uppercase;
    border-top: 0.5px solid var(--gray);
}
img {
    width: 50%;
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
}
h5, a {
    font-size: 1em;
}
ul {
    gap: 1.2em;
    text-align: center;
}

/* portrait tablets, large phones  */
@media screen and (min-width: 600px) {

}

/* landscape tablets */
@media screen and (min-width: 768px) {
    .footer-upper {
     flex-direction: row;
    justify-content: flex-start;
    align-items: flex-start;
    gap: 7em;
    padding: 5em 0;
    }
    img {
        width: 45%;
    }
    h5, a {
        font-size: 0.9em;
    }
    ul {
        text-align: left;
    }
}

/* laptops and desktops */
@media screen and (min-width: 992px) {
    img {
        width: 30%;
    }
    .footer-upper {
        padding: 4em 0;
    }
}

/* large screens */
@media screen and (min-width: 1200px) {
    .footer-upper {
        gap: 8em;
    }
}
</style>