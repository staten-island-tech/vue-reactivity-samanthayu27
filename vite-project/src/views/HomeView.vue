<template>
  <main> 
    <button class="shopbutton">Shop</button>
    <button class="detailsbutton" @click="showdetailspopup">Details</button>
    <button class="historybutton" @click="showhistorypopup">History</button>
    <button class="onepullbutton" @click="onepull">Wish x1</button>
    <button class="tenpullbutton" @click="tenpull">Wish x10</button>

    <div v-if="history" class="poopup">
      <button class="eXit" @click="exitpopup">X</button>
      <h1>Wish History</h1>
    </div>

    <div v-if="details" class="poopup">
      <button class="eXit" @click="exitpopup">X</button>
      <h1>Wish Details</h1>
      <h1 class="weirdheader"> 
        Limited-Time Event
      </h1>
      <h2>
        Event Wish “{banner name}” is now available. During this event wish, the red{event exclusive} character “alt name” real name(element color) as well as four-star characters “alt name” real name(element color),“alt name” real name(element color), and “alt name” real name(element color) will get a red{huge drop rate boost}! 
      </h2>
    </div>
  </main>
</template>

<script setup>
import { ref } from 'vue';

const history = ref(false);
const details = ref(false);
let nofourstarcount = 0;

const showhistorypopup = () => {
  history.value = true;
};

const showdetailspopup = () => {
  details.value = true;
};

const exitpopup = () => {
  details.value = false;
  history.value = false;
};

const onepull = () => {
  wishrates();
};

const tenpull = () => {
  multipull();
};

const wishrates = () => {
  const threefourfivedeterminator = Math.floor(Math.random() * 1000) + 1;
  console.log(threefourfivedeterminator);

  if (threefourfivedeterminator <= 16) {
    console.log('This is a five star');
    const fivestardeterminator = Math.random();
    if (fivestardeterminator <= 0.5) {
      console.log('Venti');
    } else if (fivestardeterminator <= 0.6) {
      console.log('Jean');
    } else if (fivestardeterminator <= 0.7) {
      console.log('Diluc');
    } else if (fivestardeterminator <= 0.8) {
      console.log('Keqing');
    } else if (fivestardeterminator <= 0.9) {
      console.log('Mona');
    } else {
      console.log('Qiqi');
    }
  } else if (threefourfivedeterminator > 16 && threefourfivedeterminator <= 146) {
    console.log('This is a four star');
    const fourstarvalue = Math.floor(Math.random() * 17) + 1;

    if (fourstarvalue <= 2) {
      console.log('Fischl');
    } else if (fourstarvalue <= 4) {
      console.log('Xiangling');
    } else if (fourstarvalue <= 6) {
      console.log('Barbara');
    } else if (fourstarvalue <= 7) {
      console.log('Amber');
    } else if (fourstarvalue <= 8) {
      console.log('Kaeya');
    } else if (fourstarvalue <= 9) {
      console.log('Lisa');
    } else if (fourstarvalue <= 10) {
      console.log('Noelle');
    } else if (fourstarvalue <= 11) {
      console.log('Bennett');
    } else if (fourstarvalue <= 12) {
      console.log('Razor');
    } else if (fourstarvalue <= 13) {
      console.log('Beidou');
    } else if (fourstarvalue <= 14) {
      console.log('Xingqiu');
    } else if (fourstarvalue <= 15) {
      console.log('Chongyun');
    } else if (fourstarvalue <= 16) {
      console.log('Ningguang');
    } else {
      console.log('Sucrose');
    }
  } else if (nofourstarcount >= 9) {
  } else {
    console.log('This is a three star');
    const threestardeterminator = Math.floor(Math.random() * 13) + 1;
    nofourstarcount++;

    if (threestardeterminator === 1) {
      console.log('Raven Bow');
    } else if (threestardeterminator === 2) {
      console.log('Sharpshooter\'s Oath');
    } else if (threestardeterminator === 3) {
      console.log('Slingshot');
    } else if (threestardeterminator === 4) {
      console.log('Emerald Orb');
    } else if (threestardeterminator === 5) {
      console.log('Magic Guide');
    } else if (threestardeterminator === 6) {
      console.log('Thrilling Tales of Dragon Slayers');
    } else if (threestardeterminator === 7) {
      console.log('Bloodtainted Greatsword');
    } else if (threestardeterminator === 8) {
      console.log('Debate Club');
    } else if (threestardeterminator === 9) {
      console.log('Ferrous Shadow');
    } else if (threestardeterminator === 10) {
      console.log('Black Tassel');
    } else if (threestardeterminator === 11) {
      console.log('Cool Steel');
    } else if (threestardeterminator === 12) {
      console.log('Harbinger of Dawn');
    } else {
      console.log('Skyrider Sword');
    }
  }
};

const multipull = () => {
  for (let i = 0; i < 10; i++) {
    wishrates();
    console.log();
  }
};
</script>

<style scoped>
.shopbutton, .detailsbutton, .historybutton, .onepullbutton, .tenpullbutton {
  border: 2px solid #ddc78e;
  background-color: white;
  border-radius: 12px;
}

.poopup {
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

.weirdheader {
  background-color: gray;
  color: white;
}

.eXit {
  position: absolute;
  right: 10px;
  top: 5px;
}
</style>
