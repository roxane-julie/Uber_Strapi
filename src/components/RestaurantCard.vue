<template>
  <div class="restaurant--card">
    <div class="restaurant--image" :style="{ backgroundImage:'url(http://localhost:1337'+ meal.attributes.image.data.attributes.url+')'}">

    </div>
    <div class="restaurant--informations">
      <div class="top">
        <p class="name">
          {{ meal.attributes.title }}
        </p>
        <p class="note"><span>
          {{ meal.attributes.note }}
        </span></p>
      </div>
      <p class="time">
        {{ meal.attributes.drive_time }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name:"RestaurantCard",

  props: {
    meal: Object
  }
}
</script>

<style lang="scss">
.restaurant--card{
    width: 23%;
    height: 30vh;
    
    p{
      margin: 0;
    }
}
.restaurant--image{
  
  height: 70%;
  background-size: cover;
  background-position: center;
}
.restaurant--informations{
  margin: 10px 0px;
  .top{
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .note{
    background-color: #eeeeee;
    height: 30px;
    width: 30px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 0.8rem;
    border-radius: 50%;

  }
  .time{
    font-size: 0.9rem;
  }
}

</style>