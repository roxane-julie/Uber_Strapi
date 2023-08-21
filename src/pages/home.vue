<template>
  <div class="home">
    <RestaurantRow />
  </div>
</template>

<script>
import RestaurantRow from '../components/RestaurantRow.vue'
export default {
  
    name:"Home",
    components:{
      RestaurantRow
    }
}
// utiliser un objet et non une chaine de caractere dans la déclaration des export
</script>

<style>

</style>