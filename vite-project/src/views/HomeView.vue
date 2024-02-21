<template>
  <main> 
    <button class="shop">Shop</button>
    <button class="details" @click="showdetailspopup">Details</button>
<!--     acts as an event listener, says that if the details button is clicked then run the function(?) -->
    <button class="history">History</button>
    <button class="onepull">Wish x1</button>
    <button class="tenpull">Wish x10</button>

    <div v-if="poopup" class="poopup">
      <!-- v-if acts as a semi(?) if else statement. If the interactive element is false, then the function that -->
      <button class="eXit" @click="exitpopup">X</button>
      <h1>
        Wish Details
      </h1>
      <h1 class="weirdheader"> 
        Limited-Time Event
      </h1>
      <h2>
        Event Wish “{banner name}” is now available. During this event wish, the red{event exclusive} character “alt name” real name(element color) as well as four star characters “alt name” real name(element color),“alt name” real name(element color), and “alt name” real name(element color) will get a red{huge drop rate boost}! 
      </h2>
      <!-- acts as an event listener, says that if the close button is clicked then run the function-->
    </div>
  </main>
</template>

<script setup>
import { ref } from 'vue';
//reactive thingy

const poopup = ref(false);
//sets the poopup thing value thing to false

const showdetailspopup = () => {
  poopup.value = true;
};
//sets the poop up thing value thing to true which means that the popup will show on the screen

const exitpopup = () => {
  poopup.value = false;
};
//sets the poopup value thing to false which means that the popup thing will not show on the screen 

</script>

<style scoped>
.shop, .details, .history, .onepull, .tenpull {
  border: 2px solid #ddc78e;
  background-color: white;
  border-radius: 12px;
}

.poopup{
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 20px;
  background-color: white;
  border: 2px solid black;
  border-radius: 2px;
  color: black;
}

.weirdheader{
  background-color: gray;
/*   change later or smthg */
  color: white;
}

.eXit{
  position: absolute;
  right: 10px;
  top: 5px;
}

</style>