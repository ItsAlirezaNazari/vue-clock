<template>
  <div class="container">
    <card-component></card-component>
  </div>
</template>

<script setup>
import CardComponent from "./components/card-component.vue";
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
  border: none;
  outline: none;
  list-style-type: none;
  text-decoration: none;
}

html {
  font-size: 16px;
}

body {
  font-family: "Barlow", sans-serif;
  font-weight: normal;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #cacae0;
}
</style>
