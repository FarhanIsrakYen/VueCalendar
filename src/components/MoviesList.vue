<template>
    <div class="m-auto">
    <h1 class="text-6xl text-center">Favourite {{moviesCount}}</h1>
    <!-- colon also mean v-bind -->
    <!-- <h2>{{ fullname }}</h2>
    <h2>{{ fname }} {{ lname }}</h2> -->
    <ul>
      <li class="flex justify-between" v-for="(fmovies,index) in movies" v-bind:key="(fmovies.name)">
        <div>
          {{index+1}} .{{ fmovies.name }}
        </div>
        <button v-on:click="remove(index)">X</button>
      </li>
    </ul>
    <form class="mt-10" @submit.prevent="addMovie">
      <input class="border rounded" v-model="newMovie" placeholder="Type name of the movie"/>
      <button class="border rounded bg-gradient-to-r from-red-700 to-pink-500 ml-5 text-white" type="submit">Add Movies</button>
    </form>
    <!-- <button @click="setFullName">Set Full Name</button>
    <small>Total Movies {{moviesCount}}</small> -->
  </div>
</template>

<script>
export default {
    computed:{
    moviesCount(){
      return this.movies.length + " Movies";
    },
    // fullname:{
    //   get(){
    //     return 'Full name is '+this.fname+' '+this.lname;
    //   },
    //   set(fullname){
    //     const values = fullname.split(" ");
    //     this.fname = values[0];
    //     this.lname = values[1];
    //   } 
    // },
  },
  methods:{
    addMovie(){
      if (this.newMovie!="") {
        this.movies.unshift({name:this.newMovie});
        this.newMovie = '';
        // alert("Sure?");
      } else {
        alert("Empty")
      }
    },
    remove(index){
      this.movies = this.movies.filter((fmovies,i) => i !=index);
    },
    // setFullName(){
    //   this.fullname = "Hello World Again"
    // }
  },
    data() {
    return{
      newMovie: "",
      // fname:"Farhan",
      // lname: "Israk",
      movies: [
        { name:"Interesteller"},
        { name:"Inception"},
        { name: "Endgame"}
      ],
    }
  }
}
</script>

<style>

</style>