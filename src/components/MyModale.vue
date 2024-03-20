<script setup>
import { ref } from "vue";
import { onClickOutside } from "@vueuse/core";

const props = defineProps({
  isOpen: Boolean,
  toDisplay: Number,
  jobs: Array,
});
const emit = defineEmits(["modal-close"]);
const target = ref(null);

onClickOutside(target, () => emit("modal-close"));
</script>

<template>
  <div v-if="isOpen" class="modal-mask">
    <div class="cadre" ref="target">
      <div>
        <slot name="boutton">
          <button @click.stop="emit('modal-close')" class="boutton">
            <h4>x</h4>
          </button>
        </slot>
      </div>
      <div class="nom">
        <slot name="titre"> {{ jobs[toDisplay].nom }} </slot>
      </div>
      <div>
        <slot name="content">
          <p class="p">Date de création: {{ jobs[toDisplay].date }}</p>
          <p class="p">
            Technologies utilisées: {{ jobs[toDisplay].technologies }}
          </p>
        </slot>
      </div>
    </div>
  </div>
</template>

<style scoped>
.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
}
.cadre {
  font-family: "AbeeZee";

  align-items: center;
  width: 400px;
  margin: 150px auto;
  padding: 20px 30px;
  text-align: center;
  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
}
.p {
  font-size: 20px;
}
.boutton {
  background-color: red;

  width: 23px;
  height: 24px;
  border-top-width: 0px;
  border-top-style: solid;
  border-bottom-width: 0px;
  border-bottom-style: solid;
  border-left-width: 0px;
  border-left-style: solid;
  border-right-width: 0px;
  border-right-style: solid;
  margin-left: 325px;
  margin-top: 0px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: grab;
}
h4 {
  color: aliceblue;
  margin-bottom: 5px;
}
.nom {
  margin-bottom: 35px;
  margin-top: 14px;
  font-family: "AbeeZee";
  font-size: 30px;
}
</style>
