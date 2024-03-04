<template>
  <body>
    <img class="background-image" src="https://static0.gamerantimages.com/wordpress/wp-content/uploads/2024/01/nahida-rerun-4-4.jpg?q=50&fit=crop&w=1500&dpr=1.5" alt="">
    <div class="content">
      <div class="buttonstuff">
        <button class="detailsbutton" @click="showdetailspopup">Details</button>
        <button class="historybutton" @click="showhistorypopup">History</button>
        <button class="onepullbutton" @click="() => wishrates(NahidaC)">Wish x1</button>
        <button class="tenpullbutton" @click="() => multipull(NahidaC)">Wish x10</button>
      </div>

      <div v-if="history" class="poopup">
        <button class="eXit" @click="exitpopup">X</button>
        <h1>Wish History</h1>
        <ul>
            <li v-for="(item, index) in wishHistory.slice().reverse()" :key="index">{{ item }}</li>
      </ul>
      </div>

      <div v-if="details" class="poopup">
        <button class="eXit" @click="exitpopup">X</button>
        <h1>Wish Details</h1>
        <h1 class="weirdheader">Limited-Time Event</h1>
        <h2>
          Event Wish "The Moongrass Enligtenment" is now available. During this event wish, the event-exclusive 5-star character "Physic of Purity" Nahida (Dendro) as well as 4-star characters "Leonine Vanguard" Gaming (Pyro), "Chivalric Blossom" Noelle (Geo), and "Enigmatic Machinist" Faruzan (Anemo) will get a huge drop-rate boost!
        </h2>
        <h2>
          ※ In most cases, the base probability of all characters and weapons is evenly distributed. If there is a boost or guarantee in effect, please refer to the corresponding rules. 
        </h2>
      </div>
    </div>
  </body>
</template>

<script setup>
import { ref } from 'vue';


const NahidaC = {
   rateupfivestar: "Nahida",
   rateupfourstar: ["Gaming", "Faruzan", "Noelle"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   regfourstars: ["Lynette", "Sayu", "Shikanoin Heizou", "Sucrose", "Charlotte", "Chongyun", "Diona", "Freminet", "Layla", "Kaeya", "Mika", "Rosaria", "Collei", "Kaveh", "Kirara", "Yaoyao", "Beidou", "Dori", "Fischl", "Kujou Sara", "Kuki Shinobu", "Lisa", "Razor", "Gorou", "Ningguang", "Yunjin", "Barbara", "Candace", "Xingqiu", "Amber", "Bennett", "Chevreuse", "Thoma", "Xiangliang", "Xinyan", "Yanfei", "Eye of Perception", "Sacrificial Bow", "Favonius Warbow", "Favonius Codex", "Favonius Greatsword", "The Bell", "The Flute", "Sacrificial Fragments", "Sacrificial Sword", "Sacrificial Greatsword", "Rainslasher", "Dragon's Bane", "Rust", "Favonius Sword", "The Stringless", "The Widsith", "Favonius Lance", "Lion's Roar"],
   threestars: ["Slingshot", "Raven Bow", "Sharpshooter's Oath", "Ferrous Shadow", "Cool Steel", "Harbinger of Dawn", "Skyrider Sword", "Bloodtainted Greatsword", "Debate Club", "Black Tassel", "Magic Guide", "Thrilling Tales of Dragon Slayers", "Emerald Orb",],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2024/01/nahida-rerun-4-4.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   cardimg: 'https://genshin.honeyhunterworld.com/img/nahida_073_gacha_card.webp?x28602',
 }

const history = ref(false)
const details = ref(false)
const wishHistory = ref([])

const showhistorypopup = () => {
  history.value = true
}

const showdetailspopup = () => {
  details.value = true
}

const exitpopup = () => {
  details.value = false
  history.value = false
}

let nofourstar = 0;

const wish = (character) => {

  if (nofourstar === 9) {
    nofourstar = 0;
    const guaranteed = Math.floor(Math.random() * 1000) + 1;

    if (guaranteed <= 6) {
      const rngfivestar = Math.floor(Math.random() * 2) + 1;
      if (rngfivestar === 1) {
        nofourstar = 0;
        return character.rateupfivestar;
      } else {
        nofourstar = 0;
        return character.regfivestars[Math.floor(Math.random() * character.regfivestars.length)];
      }
    } else {
      const rngFourStar = Math.floor(Math.random() * 2) + 1;
      if (rngFourStar === 1) {
        nofourstar = 0;
        return character.rateupfourstar[Math.floor(Math.random() * character.rateupfourstar.length)];
      } else {
        nofourstar = 0;
        return character.regfourstars[Math.floor(Math.random() * character.regfourstars.length)];
      }
    }
  }

  const rng = Math.floor(Math.random() * 1000) + 1;

  if (rng <= 6) {
    const rngfivestar = Math.floor(Math.random() * 2) + 1;
    if (rngfivestar === 1) {
      nofourstar = 0;
      return character.rateupfivestar;
    } else {
      nofourstar = 0;
      return character.regfivestars[Math.floor(Math.random() * character.regfivestars.length)];
    }
  } else if (rng > 6 && rng <= 51) {
    const rngFourStar = Math.floor(Math.random() * 2) + 1;
    if (rngFourStar === 1) {
      nofourstar = 0;
      return character.rateupfourstar[Math.floor(Math.random() * character.rateupfourstar.length)];
    } else {
      nofourstar = 0;
      return character.regfourstars[Math.floor(Math.random() * character.regfourstars.length)];
    }
  } else {
    if (character.threestars && character.threestars.length > 0) {
      const pool = Math.floor(Math.random() * character.threestars.length);
      nofourstar++;
      return character.threestars[pool];
    }
  }
};


const wishrates = (character) => {
  const result = wish(character)
  wishHistory.value.push(result);
  console.log(result)
}

const multipull = (character) => {
  for (let i = 0; i < 10; i++) {
    wishrates(character)
  }
}

</script>

<style scoped>
.background-image {
  width: 100vw;
  height: calc(100vh - 40px);
  object-fit: cover;
}
 .detailsbutton, .historybutton, .onepullbutton, .tenpullbutton {
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
  right: 10px;
  top: 5px;
}

.buttonstuff {
  position: fixed;
  bottom: 10px;
  right: 10px;
  z-index: 900;
}
</style>
