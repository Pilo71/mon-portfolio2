<template>
  <section>
    
    <div>
      <RouterLink to="/">
      <img
        class="erreur hover"
        src="../assets/img/logo2.png"
        alt="mon logo"
        title="retour à la page d'accueil"
      />
    </RouterLink>
      <h2>404</h2>
      <p>erreur! <br />cette page n'existe pas</p>
    </div>
  </section>
</template>

<script setup>
import { RouterLink } from "vue-router";
</script>
<style scoped>
img {
  
  margin-left: 350px;
  transform: rotate(-0.5turn);
  opacity: 0.6;
  width: 180px;
  height: 155px;
  filter: drop-shadow(40px 5px 10px rgba(0, 0, 0, 0.25));
}
img:hover {
  margin-left: 350px;
  transform: rotate(-0.155turn);
  cursor: grab;
}
div {
  padding: 10px;
  border-radius: 20px;
  background-color: rgba(255, 255, 255, 0.116);
  
  width: 75%;
  margin: 5rem auto;
}
h2 {
  color: #fede8c;
  font-size: 65px;
  text-align: center;
}
p {
  color: #fede8c;
  font-size: 40px;
  text-align: center;
}
@media screen and (max-width: 600px){
  img {
  
  margin-left: 40px;
  transform: rotate(-0.5turn);
  opacity: 0.6;
  width: 120px;
  height: 120px;
  filter: drop-shadow(40px 5px 10px rgba(0, 0, 0, 0.25));
}
img:hover {
  margin-left: 50px;
  transform: rotate(-0.155turn);
  cursor: grab;
}
}
</style>