<template>
  <div class = "cardcontainer">
    <div class = "card">
      <h2>{{ Destination.name }}</h2>
      <img :src="Destination.profileimg" alt="" />
      <button class = "moreinfo">More info</button>
    </div>
  </div>

<!--   a modal is a popup/window thingy, add on here so that if the user clicks the moreinfo thing info comes up-->

  </template>
  
  <script setup>
  import { ref } from "vue";
  const props = defineProps({
    Destination: Object,
  });

  </script>
  
  <style scoped>
  img {
    width: 250px;
    height: 250px;
    object-fit: cover;
  }

  .cardcontainer{
    display: flex;
    align-items: center;
    text-align: center;
    flex-wrap: wrap;
   justify-content: space-around;
/*    smthg spicys going on here  */
  }

  .card{
    height: 375px;
    width: 250px;
    text-align: center;
  }

  .moreinfo{
    border-radius: 10px;
    padding: 10px 24px;
  }
  </style>