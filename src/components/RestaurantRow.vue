<template>
  <div class="restaurant--row">
    <h2 class="title">
        Nos restaurants
    </h2>
    <div class="wrapper--card">
      <!-- <RestaurantCard v-for="(card, index) in 3" :key="index"/> -->
      <RestaurantCard v-for="(restaurant, index) in DataRestaurants" :key="index" :meal="restaurant"/>
    </div>
  </div>
</template>

<script>
import RestaurantCard from './RestaurantCard.vue';
import { computed } from 'vue';
export default {
    name: "RestaurantRow",
    components:{
      RestaurantCard,
    },
    props:{
      maprops: Array
    },
    data(){
      return {
        DataRestaurants: [],
      };
    },
    async mounted() {
      try {
          const url=  'http://localhost:1337/api/restaurants/?populate=*';
          const response = await fetch(url);
          const data = await response.json();
          const arrayData = data.data;
          this.DataRestaurants = arrayData;
          console.log(arrayData);
          console.log(this.DataRestaurants);
      } catch (error) {
        console.error(error);
      }
    },
    // computed: {
    //   computedRow(){
    //     const rows = [];
    //     for( let i = 0; i< this.DataRestaurants.length; i +=3){
    //       rows.push(this.DataRestaurants.slice(i, i + 3));
    //     }
    //     return rows
    //   },
    // },
    };
    
</script>

<style lang="scss">
.restaurant--row {
  .wrapper--card{
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;

  }
}

</style>