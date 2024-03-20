<script setup>
import { ref } from "vue";
import MyModale from "../components/MyModale.vue";
const works = ref([
  {
    nom: "CV en ligne",
    date: "10/06/2023",
    technologies: "Html5,Css3",
    image: "work-1",
  },
  {
    nom: "Cahier des charges",
    date: "10/08/2023",
    technologies: "Photoshop",
    image: "work-2",
  },
  {
    nom: "Dynamisme d'un site",
    date: "10/09/2023",
    technologies: "Html5,css3,j.s.",
    image: "work-3",
  },
]);
const itemToDisplay = ref(null);
const isModalOpened = ref(false);
const openModal = (e) => {
  itemToDisplay.value = e.target.id;
  isModalOpened.value = true;
};
const closeModal = () => {
  isModalOpened.value = false;
};
</script>

<template>
  <section id="myworks" class="titre">
    <h1 class="marge">Projets</h1>
    <div>
      <h2>Explorez quelques exemples !</h2>
      <div class="flex">
        <a href="https://github.com/Pilo71/Mon-CV.git" target="_blank"
          ><img
            src="../assets/img/github.png"
            alt="Logo de GitHub"
            title="Cv en ligne"
            class="taille"
        /></a>
        <a
          href="../../src/assets/Classeur Cahier des charges.pdf"
          target="_blank"
          ><img
            src="../assets/img/pdf.png"
            alt="Logo de LinkedIn"
            title="Cahier des charges"
            class="taille"
        /></a>
        <a
          href="https://github.com/Pilo71/devoirdynamiercommentairesjs.git"
          target="_blank"
          ><img
            src="../assets/img/github.png"
            alt="Logo de GitHub"
            title="Dynamisme d'un site communautaire"
            class="taille"
        /></a>
      </div>
    </div>

    <div v-for="(work, index) in works" class="projets">
      <button @click="openModal">
        <img
          :src="`../../src/assets/img/${work.image}.jpg`"
          :id="index"
          :alt="`${work.image}`"
        />
      </button>
    </div>
    <MyModale
      :to-display="Number(itemToDisplay)"
      :jobs="works"
      :isOpen="isModalOpened"
      @modal-close="closeModal"
      name="first-modal"
    >
      <template #titre> </template>
      <template #content> </template>

      <template #boutton> </template>
    </MyModale>
  </section>
</template>
<style scoped>
button {
  display: block;
  width: fit-content;
  margin: auto;
  margin-top: 1rem;
  margin-bottom: 1rem;
}
img {
  display: block;
  width: 330px;
  height: 450px;
  margin: auto;
}
img:hover {
  box-shadow: 10px 5px 5px rgba(10, 10, 10, 0.3);
  cursor: pointer;
}
section {
  padding-bottom: 3%;
  width: 75%;
  margin: 5rem auto;
  background-color: #34485c;
  box-shadow: 19px 19px 15px 3px rgba(1, 4, 65, 0.3);
}
.titre {
  display: flex;

  flex-direction: column;
  align-items: center;
}
.projets {
  width: 90%;
  margin: auto;
  background-color: #2c3e50;
  display: flex;
  justify-content: space-evenly;
}
.taille {
  width: 45px;
  height: 45px;
  margin-right: 10px;
  margin-bottom: 10px;
  background-color: #2c3e50;
  border-radius: 15px;
  display: flex;
  justify-content: space-evenly;
}

.marge {
  margin-top: 22px;
}
.flex {
  display: flex;
  justify-content: center;
}
</style>
