<template>
  <header>
    <a href="#acceuil"
      ><img class="photo" src="../assets/img/mon logo.png" alt="mon" logo
    /></a>
    <h4>{{ title }}</h4>

    <a href="#" @click="toggle" class="toggle-button">
      <span class="bar"></span>
      <span class="bar"></span>
      <span class="bar"></span>
    </a>
    <ul v-if="show">
      <li>
        <a class="nav" href="#aboutme">À propos </a>
      </li>

      <li>
        <a class="nav" href="#myworks">Projets</a>
      </li>
      <li>
        <a class="nav" href="#contact">Contact</a>
      </li>
    </ul>
  </header>
</template>

<script setup>
import { ref } from "vue";

const show = ref(true);
const title = import.meta.env.VITE_APP_TITLE;
function toggle() {
  show.value = !show.value;
}
let windowWidth = window.innerWidth;
if (windowWidth < 600) {
  show.value = false;
}
</script>

<style scoped>
header {
  display: flex;
  top: 0;
  left: 0;
  right: 0;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  width: 100%;
  background-color: #2c3e50;
}

.router-link-active {
  text-decoration: underline;
  text-underline-offset: 8px;
}
.photo {
  width: 60px;
  height: 45px;
  margin: 0.5rem 2rem;
}

.photo:hover {
  background-color: aquamarine;
}
header ul {
  display: flex;
  width: 50%;
  justify-content: space-evenly;
  padding: 0px;
  list-style-type: none;

  margin-right: 20%;
}
.nav {
  padding: 1rem;
  display: block;

  color: #c4ebd3;
  font-family: "AbeeZee";
  text-decoration: none;
}
.nav:hover {
  color: khaki;
}

.toggle-button {
  position: absolute;
  display: none;
  top: 0.75rem;
  right: 1rem;
  flex-direction: column;
  justify-content: space-between;
  width: 30px;
  height: 20px;
}
.toggle-button .bar {
  height: 3px;
  width: 100%;
  background-color: white;
  border-radius: 10px;
}
h4 {
  color: #c4ebd3;
  font-family: "AbeeZee";
  font-size: 20px;
}
@media screen and (max-width: 600px) {
  .toggle-button {
    display: flex;
  }
  header {
    flex-direction: column;
  }
  header ul {
    width: 100%;
    flex-direction: column;
    margin-left: 20%;
  }
  header li {
    text-align: center;
  }
  header li a {
    padding: 5rem 1rem;
  }
  header .active {
    display: flex;
  }
}
</style>
