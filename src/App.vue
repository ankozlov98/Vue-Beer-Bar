<template>
  <main id="app">
    <article class="common-bg-color">
      <section class="main-heading">
        <h1>Hello</h1>
      </section>
      <section class="all-info-container">
        <PersonBox
          :person="person"
          :job="person_job"
          :adress="person_address"
          :subscription="person_subscription"
          v-if="person"
        />

        <BeerBox
          :beer="beer"
          :handleBeerChange="handleBeerChange"
          :opinion="opinion"
          v-if="beer && opinion"
        />
      </section>
    </article>
  </main>
</template>



<script>



import "./assets/styles/person_card.css";
import "./assets/styles/template.css";
import "./assets/styles/hover.css";
import "./assets/styles/beer_card.css";


import "./assets/styles/modal_view.css";
import "./assets/styles/media_query.css";


import PersonBox from "./components/PersonBox.vue";
import BeerBox from "./components/BeerBox.vue";

export default {
  name: "app",
  components: {
    PersonBox,
    BeerBox,
  },

  data() {
    return {
      url_base_person: "https://random-data-api.com/api/users/random_user",
      url_base_beer: "https://random-data-api.com/api/beer/random_beer",

      person: {},
      person_job: {},
      person_address: {},
      person_subscription: {},

      beer: {},
      opinion: 0,
      
    };
  },
  mounted() {
    this.fetchPerson();
    this.fetchBeer();

    this.opinion = this.getRandomInt(90, 100);
  },
  components: { PersonBox, BeerBox },
  methods: {
    getRandomInt(min, max) {
      min = Math.ceil(min);
      max = Math.floor(max);
      return Math.floor(Math.random() * (max - min)) + min;
    },
    fetchPerson() {
      fetch(this.url_base_person)
        .then((res) => {
          return res.json();
        })
        .then((res) => {
          this.person = res;
          this.person_job = res.employment;
          this.person_address = res.address;
          this.person_subscription = res.subscription;
        });
    },
    fetchBeer() {
      fetch(this.url_base_beer)
        .then((res) => {
          return res.json();
        })
        .then((res) => {
          this.beer = res;
        });
      this.opinion = this.getRandomInt(90, 100);
    },
    handleBeerChange() {
      this.getRandomInt();
      this.fetchBeer();
      this.opinion = this.getRandomInt(90, 100);
    },
  },
};
</script>


<style>
</style>
