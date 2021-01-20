<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Giveaway!</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>  
  </div>

  <div v-if="showModal2">
    <Modal theme="info" @close="toggleModal2">
      <template v-slot:links>
        <a href="#">latest news</a>
        <a href="#">forum posts</a>
      </template>
      <h1>Information!</h1>
      <p>Keep in touch with us!</p>
    </Modal>
  </div>

  <button @click="toggleModal">open modal</button>
  <br>
  <br>
  <button @click="toggleModal2">open 2nd modal</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App :)',
      header: 'Sign up for the Giveaway!',
      text: 'Grab your ninja swag for half price!',
      showModal: false,
      showModal2: false
    } 
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },

    toggleModal() {
      this.showModal = !this.showModal
    },

    toggleModal2() {
      this.showModal2 = !this.showModal2
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
