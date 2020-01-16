<template>
  <div id="app">
    <h1>Brew Dog Beers</h1>
    <div class="main-container">
      <all-beers-list :beers='beers'></all-beers-list >
        <!-- <beer-detail :rendered-beer="selectedBeer"></beer-detail > -->
          <!-- <favourite-beers-list :favourite-beers="favouriteBeers"></favourite-beers-list > -->
          </div>
        </div>
      </template>

      <script>
      import {eventBus} from './main.js'

      import AllBeersList from './components/AllBeersList.vue'

      export default {
        name: 'app',
        data() {
          return {
            beers: [],
            // favouriteBeers: [],
            selectedBeerId: null
          }
        },
        mounted() {
          fetch('https://api.punkapi.com/v2/beers')
            .then(response => response.json())
            .then(beers => this.beers = beers)

            eventBus.$on('beer-selected', (beer)=> {
              this.selectedBeer = beer
            })
        },
        components: {
          "all-beers-list": AllBeersList
          // "beer-detail": BeerDetail,
          // "favourite-beers-list": FavouriteBeersList
        },
        computed: {
          renderBeer: function () {
            return this.beers.find(beer => beer.id === this.selectedBeerId)
          }
        }
      }
      </script>

      <style>
        /* #app {
          font-family: 'Avenir', Helvetica, Arial, sans-serif;
          -webkit-font-smoothing: antialiased;
          -moz-osx-font-smoothing: grayscale;
          text-align: center;
          color: #2c3e50;
          margin-top: 60px;
        } */
        .main-container {
          display: flex;
          justify-content: space-between;
        }
      </style>
