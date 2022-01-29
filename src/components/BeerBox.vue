<template>

<section class="beer-box info-container">

          <section class='beer-box-heading'>
            <section class="beer-box-name">{{beer.name}}</section>
            <section class="beer-box-brand">{{beer.brand}}</section>
          </section>

          <section class="beer-box-opinion">We Think It Is {{opinion}}% Match </section>

    <section class="beer-box-info"> 
            <section class="beer-box-table">
                <table>
                  <thead>
                      <td>Criteria</td>
                      <td>Value</td>
                  </thead>
                  <tr>
                    <td>Identification</td>
                    <td>{{beer.id}}</td>
                  </tr>
                  <tr>
                    <td>Style</td>
                    <td>{{beer.style}}</td>
                  </tr>
                  <tr>
                    <td>Alcohol</td>
                    <td>{{beer.alcohol}}</td>
                  </tr>
                  <tr>
                    <td>Yeast</td>
                    <td>{{beer.yeast}}</td>
                  </tr>
                </table>
              </section>
              <section class="beer-box-buttons">
                  <button v-on:click="handleBeerChange" class="beer-box-single-button">Change</button>
                  <button class="beer-box-single-button">Learn More</button>
              </section>
              <section class="beer-box-social-media"></section>
          </section>
          </section>
</template>

<script>


export default ({
     name: 'BeerBox',
     props: ['handleBeerChange', 'beer', 'opinion'],
     

})
</script>
