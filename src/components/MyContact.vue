<script setup>
import emailjs from "@emailjs/browser";
import { ref } from "vue";

function sendEmail() {
  (() => {
    emailjs.init(import.meta.env.VITE_EMAILJS_PUBLIC_KEY);
  })();

  const params = {
    to_name: "Pilorger",
    from_name: document.querySelector("#senderName").value,
    from_email: document.querySelector("#senderEmail").value,
    message: document.querySelector("#emailMessage").value,
    reply_to: document.querySelector("#senderEmail").value,
  };

  const serviceID = import.meta.env.VITE_EMAILJS_SERVICEID;
  const templateID = import.meta.env.VITE_EMAILJS_TEMPLATEID;
  emailjs
    .send(serviceID, templateID, params)
    .then((res) => {
      alert("L'e-mail a été envoyé avec succès");
    })
    .catch();
}
function clearForm() {
  return {
    errors: [],
    form: {
      senderName: null,
      senderEmail: null,
      senderMessage: null,
    },
  };
}
</script>

<template>
  <section id="contact">
    <div class="titre">
      <h1 class="marge">Contact</h1>
      <h2>Remplissez notre formulaire afin d'établir un premier contact !</h2>
    </div>

    <div class="form">
      <form
        ref="anyName"
        @submit.prevent="sendEmail() && clearForm()"
        id="contact"
      >
        <div class="colonnes">
          <label for="first-name">Nom et Prénom</label>
          <input
            class="style"
            type="text"
            name="firstName"
            id="senderName"
            required
            minlength="1"
          />
        </div>
        <div class="colonnes">
          <label for="e.mail">e.mail</label>

          <input
            class="style"
            type="email"
            name="e.mail"
            id="senderEmail"
            required
            minlength="1"
          />
        </div>

        <div class="colonnes">
          <label for="message">Message</label>
          <textarea
            class="style2"
            type="text"
            name="message"
            id="emailMessage"
            required
            minlength="1"
            maxlength="300"
          ></textarea>
        </div>
        <div class="colonnes">
          <input class="bouton" type="submit" value="Envoyer" />
        </div>
      </form>
      <div id="error-message" style="display: none">
        <h2>Tous les champs doivent étre remplis</h2>
      </div>
    </div>
  </section>
</template>
<style scoped>
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
  justify-content: center;
}
.marge {
  margin-top: 30px;
}
.form {
  width: 90%;
  margin: auto;
  background-color: #2c3e50;
}
.colonnes {
  display: flex;
  flex-direction: column;

  margin-left: 5%;
  padding-top: 2%;
  padding-bottom: 3%;
  text-align: center;
  align-items: center;
  font-family: "AbeeZee";
  font-size: 20px;
  color: white;
}
input {
  width: 45%;
}
textarea {
  width: 50%;
  height: 200px;
  overflow-y: scroll;
}
.bouton {
  width: 130px;

  padding: 10px;
  justify-content: center;
  align-items: center;
  gap: 10px;
  color: #c4ebd3;
  border-radius: 30px;
  border: 1px solid rgba(0, 0, 0, 0.5);
  background-color: #34485c;
}
.bouton:hover {
  box-shadow: 0 0 6px 6px aquamarine;
  cursor: grab;
}
</style>
