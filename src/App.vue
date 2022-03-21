<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <h1>{{ this.title }}</h1>
  <div v-if="showModal">
    <Modal @close="toggleModal">
      <template v-slot:header-button>
        <a @click="toggleModal">X</a>
      </template>
      <h1>Modal title</h1>
      <p>Content, this is a lot of content. Lines and stuff for my modal.</p>
      <template v-slot:footer-content>
        <p>Big promo on maxi best of menus in all Moscow's MacDonalds</p>
      </template>
    </Modal>
  </div>
  <div v-if="showModal2">
    <Modal @close="toggleModal2">
      <template v-slot:header-button>
        <a @click="alertPlus">+</a>
      </template>
      <h1>Second modal</h1>
      <p>Second / Second / Second</p>
    </Modal>
  </div>
  <button @click="toggleModal">Show modal</button>
  <button @click="toggleModal2">Show second modal</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: "This is Vue !",
      showModal: false,
      showModal2: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2;
    },
    alertPlus() {
      window.alert('This is an alert');
    }
  },


}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
