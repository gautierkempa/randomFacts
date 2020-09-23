<template>
  <div class="container">
    <div>
      
      <h1 class="title" @click='update()'>
        {{phrase}}
      </h1>
      <h3 class="title-2">
        Random fact using an api with nuxt
      </h3>
      
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  components: {

  },
  data(){
    return{
      phrase: "Défaut"
    }
  },

  methods:{
    update(){
      axios.get('https://uselessfacts.jsph.pl/random.json?language=en').then(reponse => this.phrase = reponse.data.text)
    }
  },

  mounted(){
    axios.get('https://uselessfacts.jsph.pl/random.json?language=en').then(reponse => this.phrase = reponse.data.text)
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 100;
  font-size: 50px;
  color: #35495e;
  letter-spacing: 1px;
  margin-left:15px;
  margin-right:15px;
}
.title-2 {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 100;
  font-size: 50px;
  color: #2980b9;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
