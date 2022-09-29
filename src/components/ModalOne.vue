<template>
  <div class="modal-bg">
    <div class="modal">
      <span
        @click="closeModal()"
        class="close-icon material-symbols-outlined">close</span>
      <h2>{{modalTitle}}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ModalOne',
  props: {
    modalId: String,
    modalTitle: String
  },
  methods: {
    closeModal() {
      this.$emit('close-modal');
    }
  }
}
</script>





<style scoped>
/* Start During End for in and out */
/* .v-enter-from {
  transform: translate(0, 20px) scale(0.9);
  opacity: 0;
}
.v-enter-active {
  transition: all 0.3s ease-in-out;
}
.v-enter-to {
  transform: translate(0, 0px);
  opacity: 1;
}
.v-leave-from {
  opacity: 1;
}
.v-leave-active {
  transition: all 0.3s ease-in-out;
}
.v-leave-to {
  opacity: 0;
  transform: translate(0, 20px) scale(0.9);
} */

.overzoom-enter-active {
  animation: vAnimation-in 0.3s;
}

.overzoom-leave-active {
  animation: vAnimation-out 1s;
}

@keyframes vAnimation-in {
  0% {
    transform: translate(0, 40px) scale(0.9);
    opacity: 0;
  }
  65% {
    transform: translate(0, -5px) scale(1.1);
    opacity: 1;
  }
  100% {
    transform: translate(0, 0) scale(1);
  }
}

@keyframes vAnimation-out {
  0% {
    transform: translate(0, 0) scale(1);
    opacity: 1;
  }
  30% {
    opacity: 0;
  }
  100% {
    transform: translate(0, 20px) scale(0);
    opacity: 0;
  }
}



.modal-bg {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 100;
  backdrop-filter: blur(4px);
}

.modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: block;
  width: 100%;
  max-width: 400px;
  background: white;
  margin: 0 auto;
  padding: 30px;
  border-radius: 8px;
  box-shadow: 0 0 30px -1px rgba(0,0,0,0.5);
}

.close-icon {
  position: fixed;
  display: block;
  top: -10px;
  right: -10px;
  background-color: white;
  width: 40px;
  height: 40px;
  line-height: 40px;
  border-radius: 100%;
  text-align: center;
  box-shadow: 0 0 15px -1px rgba(0,0,0,0.5);
  cursor: pointer;
  transition: all 0.3s;
}

.close-icon:hover {
  background-color: #f0f0f0;
  box-shadow: 0 0 20pxpx 0px rgba(0,0,0,0.6);
}

img {
  display: inline-block;
  vertical-align: middle;
  margin: 0 15px 0 0;
  width: 100%;
  max-width: 50px;
}

h1 {
  text-align: center;
}

</style>