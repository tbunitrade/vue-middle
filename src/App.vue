<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/movies">Movies</router-link>
  </div>
  <router-view/>
  <h2>{{h2title}}</h2>
  <p>Wellcome ...</p>
  <div v-if="showModal">
    <Modal  :header="header" :text="text" :body="['shantaram',4]" theme="sale" @close="toggleModal" />
  </div>
  <button @click="showModal = true">Open modal</button>
  <button @click.alt="toggleModal">Open modal alt</button>
</template>

<script>
import Modal from '@/components/Modal.vue'

export default {
  name : 'App',
  components: {Modal},
  data() {
    return {
      h2title : 'Sonich app',
      header : 'Sign up form the Giveaway',
      text: 'Grab some data',
      showModal: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal= !this.showModal;
    }
  }
  
}
</script>


<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
