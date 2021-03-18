<template>
  <div class="hello">
     <p> Tongasoa </p>
      <div :key="index" v-for="(pays,index) in pays">
        <h1>{{ pays.translations.fr }}</h1>
       <!-- <img :src="pays.flag">--> 
      </div> 
  </div>
</template>

<script>
import axios from 'axios'



export default {
  name: 'HelloWorld',
  data(){
    return{
       pays: null,
    } 
  },
  mounted(){
    axios
    .get('https://restcountries.eu/rest/v2/all')
    .then((reponse) =>{
      this.pays = reponse.data;
      console.log(this.pays)
    });
    
  },
 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
