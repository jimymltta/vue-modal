<template>
  <h1>{{ title }}</h1>
  <p>Welcome :)</p>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">More infos</a>
      </template>
      <h1>Ninja Givaway!</h1>
      <p>Grab your Ninja swag for half price!</p>
    </Modal>
  </teleport>

  <div v-if="showModal2">
    <Modal @close="toggleModal2">
      <h1>Hello there!</h1>
      <p>How's this second modal? Good, right?</p>
    </Modal>
  </div>

  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModal2">Open Modal 2</button>
</template>

<script>
import Modal from './components/Modal.vue';

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My first Vue App',
      header: 'Sign up for our giveaway!',
      text: 'Grab your Ninja swag for half price!',
      showModal: false,
      showModal2: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2;
    },
  },
};
</script>

<style>
#app,
.modals {
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
