<template> 
<main id="app">
  <article class="common-bg-color">
      <section class="heading">
        <h1>Hello</h1>
      </section>
      <section class="all-info-container">
        <PersonBox :person="person" v-if="person" />
        

        <section class="beer-box info-container">
          <section class="beer-box-opinion" v-if="opinion">We Think It Is {{opinion}}% Match </section>
          <h2 v-if="beer">{{beer.name}}</h2>
          <button v-on:click="handleBeerChange">Change</button>
        </section>
      </section>
      
      
  </article>
  
</main>
  
</template>



<script>

import './assets/styles/person_card.css'
import './assets/styles/template.css'
import './assets/styles/hover.css'
import './assets/styles/beer_card.css'

import PersonBox from './components/PersonBox.vue';

export default {
    name: "app",
    components: {
      PersonBox
    },

    data() {
        return {
            url_base_person: "https://random-data-api.com/api/users/random_user",
            url_base_beer: "https://random-data-api.com/api/beer/random_beer",
            person: {},
            beer: {},
            opinion: 0
        };
    },
    mounted() {
        this.fetchPerson();
        this.fetchBeer();

        this.opinion = this.getRandomInt(90,100)
    },
    components: { PersonBox },
    methods: {
      getRandomInt(min, max) {
          min = Math.ceil(min);
          max = Math.floor(max);
          return Math.floor(Math.random() * (max - min)) + min;
      },
      fetchPerson () {
            fetch(this.url_base_person)
            .then((res) => { return res.json(); })
            .then((res) => { this.person = res; });
      },
      fetchBeer() {
        fetch(this.url_base_beer)
            .then((res) => { return res.json(); })
            .then((res) => { this.beer = res; })
      },
      handleBeerChange() {
        this.getRandomInt()
        this.fetchBeer()
        this.opinion = this.getRandomInt(90,100)
      }
    }
}
   
</script>


<style>

    

</style>
