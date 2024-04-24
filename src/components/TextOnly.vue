<template>
    <div class="container">
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
    width: 100%;
}
p {
    margin: 0;
    height: 100%;
    text-align: justify;
}
.container {
    display: flex;
    flex-direction: column;
    text-align: center;
    gap: 0;
}

/* portrait tablets, large phones  */
@media screen and (min-width: 600px) {
    h2 {
    min-width: 40%;
}
    h2, p {
        text-align: left;
    }
    .container {
    flex-direction: row;
    gap: 1.8em;
    align-items: center;
}
}

/* landscape tablets */
@media screen and (min-width: 768px) {

}

/* laptops and desktops */
@media screen and (min-width: 992px) {
    h2 {
        min-width: 50%;
    }
    .container {
        gap: 2em;
    }
}

/* large screens */
@media screen and (min-width: 1200px) {
  }
</style>