<template>
  <button
    @click="showModal = !showModal"
  >Show Modal One</button>

  <transition name="overzoom">
    <ModalOne 
      modalTitle="Modal One"
      modalId="modal-one"
      v-if="showModal"
      @close-modal="showModal = !showModal"
    />
  </transition>

</template>

<script>
import ModalOne from '@/components/ModalOne.vue'

export default {
  name: 'App',
  components: {
    ModalOne
  },
  data() {
    return {
      showModal: false
    }
  }
}
</script>









<style>

.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Rubik', sans-serif;
}

#app {
  width: 100vw;
  height: 100vh;
  max-width: 600px;
  padding: 50px;
}

button {
  cursor: pointer;
  display: block;
  width: 100%;
  padding: 15px;
  border-radius: 5px;
  background-color: rgba(0,150,180,1);
  border: 8px solid rgba(0,180, 210,0.5);
  color: white;
  font-size: 18px;
  font-weight: 700;
  transition: all 0.2s;
  margin: 0 0 30px;
}
button:hover {
  background-color: rgba(0,180, 210,1);
}
button:focus {
  box-shadow: 0 0 0 8px rgba(0,210,240,0.3);
}

.material-icons {
  font-family: 'Material Icons';
  font-weight: normal;
  font-style: normal;
  font-size: 24px;  /* Preferred icon size */
  display: inline-block;
  line-height: 1;
  text-transform: none;
  letter-spacing: normal;
  word-wrap: normal;
  white-space: nowrap;
  direction: ltr;

  /* Support for all WebKit browsers. */
  -webkit-font-smoothing: antialiased;
  /* Support for Safari and Chrome. */
  text-rendering: optimizeLegibility;

  /* Support for Firefox. */
  -moz-osx-font-smoothing: grayscale;

  /* Support for IE. */
  font-feature-settings: 'liga';
}

</style>