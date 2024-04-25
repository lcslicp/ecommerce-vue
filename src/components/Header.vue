<template>
  <header class="flex-row">
    <img :src="imgSrc" alt="company logo">
    <nav :style="{ display: showMenu ? 'flex' : 'none' }">
      <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/">About Us</a></li>
        <li><a href="/">Services <svg width="15" height="7" viewBox="0 0 33 20" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M4.63988 0.119994L16.8799 12.3333L29.1199 0.119995L32.8799 3.87999L16.8799 19.88L0.879882 3.87999L4.63988 0.119994Z" fill="white"/></svg></a></li>
        <li><a href="/">Testimonials</a></li>
        <li><button class="btn-light">Contact Us</button></li>
      </ul>
    </nav>
    
    <div class="menu" @click="toggleMenu">
        <span></span>
        <span></span>
        <span></span>
      </div>

    
    <!-- <ul v-if="showMenu">
      <li><a href="/">Home</a></li>
      <li><a href="/">About Us</a></li>
      <li><a href="/">Services <svg width="15" height="7" viewBox="0 0 33 20" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M4.63988 0.119994L16.8799 12.3333L29.1199 0.119995L32.8799 3.87999L16.8799 19.88L0.879882 3.87999L4.63988 0.119994Z" fill="white"/>
</svg>
</a></li>
      <li><a href="/">Testimonials</a></li>
      <li><button class="btn-light">Contact Us</button></li>
    </ul>
    <div v-else>
      <div class="menu" @click="toggleMenu">
        <span></span>
        <span></span>
        <span></span>
      </div>
        <ul :style="{ display: showMobileMenu ? 'flex' : 'none' }">
          <li><a href="/">Home</a></li>
          <li><a href="/">About Us</a></li>
          <li><a href="/">Services <svg width="15" height="7" viewBox="0 0 33 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M4.63988 0.119994L16.8799 12.3333L29.1199 0.119995L32.8799 3.87999L16.8799 19.88L0.879882 3.87999L4.63988 0.119994Z" fill="white"/>
            </svg></a></li>
          <li><a href="/">Testimonials</a></li>
          <li><button class="btn-light">Contact Us</button></li>
        </ul>
    </div> -->
  </header>
</template>


<style scoped>
  header, ul {
    z-index: 9;
  }
  header {
    padding-top: 1.5em;
    justify-content: space-between;
    align-items: center;
    position: relative;
  }
  nav {
    position: absolute;
    display: none;
    width: 100%;
    top: 60px;
    height: fit-content;
  }
  ul {
    list-style-type: none;
    display: flex;
    flex-direction: column;
    padding: 0;
    background-color: rgba(24, 19, 23, 0.95);
    align-items: center;
    justify-content: center;
    width: 100%;
  }
  li {
    margin: 0;
    padding: 2em 0;
    border-bottom: 0.5px solid rgba(164, 164, 162, 0.2);
    width: inherit;
    text-align: center;
  }
  li:hover {
    background-color: var(--dark-gray);
  }
  a, button {
    color: var(--white);
    font-size: 2em;
    width: 100%;
    font-weight: 100;
  }
  button {
    background-color: transparent;
    padding: 0;
    height: fit-content;
  }
  button:hover {
    border: none;
  }
  .menu span {
    display: block;
    top: 0;
    right: 0;
    width: 3em;
    height: 4px;
    margin: 8px 0;
    background-color: var(--white);
  }
  /* portrait tablets, large phones  */
  @media screen and (min-width: 600px) {

  }

  /* landscape tablets */
  @media screen and (min-width: 768px) {
    a, button {
    color: var(--white);
    font-size: 1.6em;
  }
  }

  /* laptops and desktops */
  @media screen and (min-width: 992px) {
    header {
      position: static;
      padding-top: 0.8em;
    }
    .menu span {
      display: none;
    }
    nav {
      position: static;
      display: flex;
      justify-content: flex-end;
    }
    ul {
      width: 85%;
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: flex-end;
      background-color: transparent;
      gap: 3em;
    }
    li {
      margin: 0;
      padding: 0;
      border-bottom: none;
      width: fit-content;
    }
    li:hover {
      background-color: none;
    }
    a, button {
      font-size: 0.9em;
    }
    button {
      font-weight: 400;
      color: var(--black);
      background-color: var(--white);
      padding: 0.5em 2em;
      height: 2.8em;
    }
    button:hover {
      border: 1px solid var(--white);
    }
  }

  /* large screens */
  @media screen and (min-width: 1200px) {
    ul {
      gap: 5em;
    }
    }
</style>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  props: {
    imgSrc: {
      type: String,
      required: true
    },
  },
  setup(props) {
    const imgSrc = require(`@/assets${props.imgSrc}`);

    const showMenu = ref(window.innerWidth > 768);

    const toggleMenu = () => {
      showMenu.value = !showMenu.value
    }
 
    return {
      imgSrc,
      showMenu,
      toggleMenu,
    }
  }
})
</script>