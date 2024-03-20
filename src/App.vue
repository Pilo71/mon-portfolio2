<script setup>
import { RouterView } from "vue-router";
</script>

<template>
  <main id="acceuil">
    <RouterView />
  </main>
  <footer>
    <div>
      <a href="" target="_blank"
        ><img src="../src/assets/img/linkedin.png" alt="Logo de LinkedIn"
      /></a>
      <a href="" target="_blank"
        ><img src="../src/assets/img/github2.png" alt="Logo de GitHub"
      /></a>
      <a
        href="https://mail.google.com/mail/u/0/#inbox?compose=new"
        target="_blank"
        ><img src="../src/assets/img/google mail.png" alt="Logo de Google Mail"
      /></a>
    </div>
    <small> &copy;<time datetime="2024-03-18"> 18/03/2024</time> </small>
  </footer>
</template>
<style>
@import url("https://fonts.googleapis.com/css2?family=ABeeZee&family=Pacifico&family=Raleway:wght@400;600&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-size: 20px;
}
body {
  background-color: #2c3e50;
}
main {
  min-height: 100vh;
  padding-top: 30px;
  background-color: #2c3e50;
  h1 {
    color: white;
    font-family: "AbeeZee";
    font-size: 40px;
    font-style: normal;
    margin-bottom: 3%;
  }
  h2 {
    color: #c4ebd3;
    font-family: "ABeeZee";
    font-size: 25px;
    font-style: normal;
    margin-bottom: 3%;
  }
}
footer {
  padding: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
footer div {
  padding: 10px;
  border-radius: 20px;
  background-color: #34485c;
}
footer a img {
  width: 50px;
  border-radius: 50%;
  margin: auto 5px;
}
footer a:hover img {
  box-shadow: 0 0 6px 6px aquamarine;
}
small {
  justify-self: flex-start;
  margin-top: 5px;
  color: aquamarine;
}
</style>
