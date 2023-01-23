<template>
  <h1>{{title}}</h1>
  <p>Welcome...</p>
  <div v-if='showModal'>
    <Modal theme='sale' @close='toggleModal' >
      <template v-slot:links>
        <a href="#">Sign Up Now</a>
        <a href="#">More Info</a>
      </template>
      <h1>Sign up for the Giveaway</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </div>
  <div v-if='showModalTwo'>
    <Modal @close='toggleModalTwo'>
      <h1>Sign up for the Newsletter</h1>
      <p>For updates and promo codes!</p>
    </Modal>
  </div>
  <br>
  <button @click.alt="toggleModal">Open Modal (alt)</button>
  <br>
  <button @click='toggleModalTwo'>Open the Second Modal! Muahahah</button>
</template>

<script>

import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: 'My First Vue App :)',
      header: "Sign up for the Giveaway",
      text: "Grab your ninja swag for half price!",
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    }
  }
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
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
