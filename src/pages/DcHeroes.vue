<template>
  <div class="m-auto">
      <h1 class="text-2xl text-center">Dc Heros</h1>

      
      <ul>
        <li class="flex justify-between" v-for="(hero, index) in dcHeros" :key="hero.name">
          <div>{{hero.name}} </div>
          <button @click="remove(index)">x</button>
        </li>
      </ul>

      <form class="mt-10" @submit.prevent="addHero">
        <input class="border rounded" v-model.trim="newHero" placeholder="Type hero Name here">
        <button class="border rounded bg-gradient-to-r from-red-700 to-pink-500 text-white" type="submit">Add Hero</button>
      </form>

      <small>Total heros = {{herosCount}}</small>
  </div> 
</template>

<script>
export default {
    data(){
          return {
            newHero: "",
            fname: "Eddie",
              lname: "Ash",
            dcHeros: [
              { name: "Wonder Woman"},
              { name: "Superman"},
              { name: "Batman"},
              { name: "Flash"},
            ]
          }
  },
  computed: {
              herosCount(){
                return this.dcHeros.length
              },

              randC(){
                return Math.random();
              },
  },
 
 methods: {
            addHero() {
              if(this.dcHeros !== ""){
                this.dcHeros.unshift({name: this.newHero });
                this.newHero = "";
              } 
            },
 
            remove(index){
                this.dcHeros = this.dcHeros.filter((hero,i) => i !== index)
              }
 },
}
</script>

<style>

</style>