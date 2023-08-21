<template>
  <div id="opp">
    <Home/>
  </div>
</template>

<script>
import Home from "./pages/home.vue"
export default {
  name: "App",
  components: {
    Home
  }
}
</script>

<style scoped>
@import url(https://fonts.googleapis.com/css2?family=Roboto%3Awght%40300%3B400%3B700&display=swap);

#opp {
  font-family: 'Roboto', sans-serif;
  padding: 20px;

}

</style>
