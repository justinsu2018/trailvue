<template>
  <h1>{{ title }}</h1>

  <teleport to="#models" v-if="showModal">
    <!--
    <Modal :header="header" :text="text" theme="sale1" @close="toggleModal" />
    -->
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info...</a>
      </template>
      <h1>Sign up for the Giveway!</h1>
      <p>foo 2...</p>
    </Modal>
  </teleport>

  <teleport to="#models" v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Sign up for the News letter</h1>
      <p>foo 3...</p>
    </Modal>
  </teleport>

  <button @click="toggleModal">
    <span v-if="showModal">Hide Modal</span>
    <span v-if="!showModal">Show Modal</span>
  </button>

  <button @click="toggleModalTwo">
    <span v-if="showModal">Hide Modal</span>
    <span v-if="!showModal">Show Modal</span>
  </button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "My 1st Vue App",
      header: "Sign up for the Giveway!",
      text: "foo 2...",
      showModal: false,
      showModalTwo: false
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>

<style>
#app, #models {
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
