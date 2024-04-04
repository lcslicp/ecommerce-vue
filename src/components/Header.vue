<template>
  <header>
    <img src="" alt="company logo">
    <ul>
      <li><a href="/">Home</a></li>
      <li><a href="/">About Us</a></li>
      <li><a href="/">Services</a></li>
      <li><a href="/">Testimonials</a></li>
      <li><button>Contact Us</button></li>
    </ul>
  </header>
</template>


<style scoped>
header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #1c1c1c;
}
</style>
