<template>
  <header class="flex-row">
    <img :src="imgSrc" alt="company logo">
    <ul class="flex-row">
      <li><a href="/">Home</a></li>
      <li><a href="/">About Us</a></li>
      <li><a href="/">Services <svg width="15" height="7" viewBox="0 0 33 20" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M4.63988 0.119994L16.8799 12.3333L29.1199 0.119995L32.8799 3.87999L16.8799 19.88L0.879882 3.87999L4.63988 0.119994Z" fill="white"/>
</svg>
</a></li>
      <li><a href="/">Testimonials</a></li>
      <li><button class="btn-light">Contact Us</button></li>
    </ul>
  </header>
</template>


<style scoped>
header, ul {
  justify-content: space-between;
  align-items: center;
}
ul {
  list-style-type: none;
  padding: 0;
  width: 60%;
}
li {
  margin: 0;
}
a {
  color: var(--white);
  font-size: 0.95em;
}
</style>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  props: {
    imgSrc: {
      type: String,
      required: true
    },
  },
  setup(props) {
    const imgSrc = require(`@/assets${props.imgSrc}`);
    return {
      imgSrc
    }
  }
})
</script>
