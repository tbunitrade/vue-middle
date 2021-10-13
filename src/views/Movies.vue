<template>
  <div class="Movies">
    <h1>{{title }}</h1>
    <input type="text" ref="name">
    <input type="tel" ref="genre">
    <button @click="handleClick"> Click</button>
    
  </div>
</template>

<script>
export default {
    data () {
        return {
            title:'List of movies'
        }
        
    },
    methods: {
        handleClick() {
            console.log( this.$refs.genre.value)
            this.$refs.name.classList.add('active')
            this.$refs.genre.classList.add('active2')
            this.$refs.genre.focus()
        }
    }
}
</script>
