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
        <li v-for="(item, index) in wishHistory" :key="index">{{ item }}</li>
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

const pics = [
    {
        name: "Amber",
        wishimg: 'https://genshin.honeyhunterworld.com/img/ambor_021_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/ambor_021_gacha_card.webp?x28602',
    },
    {
        name: "Barbara",
        wishimg: 'https://genshin.honeyhunterworld.com/img/barbara_014_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/barbara_014_gacha_card.webp?x28602',
    },
    {
        name: "Beidou",
        wishimg: 'https://genshin.honeyhunterworld.com/img/beidou_024_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/beidou_024_gacha_card.webp?x28602',
    },
    {
        name: "Bennett",
        wishimg: 'https://genshin.honeyhunterworld.com/img/bennett_032_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/bennett_032_gacha_card.webp?x28602',
    },
    {
        name: "Candace",
        wishimg: 'https://genshin.honeyhunterworld.com/img/candace_072_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/candace_072_gacha_card.webp?x28602',
    },
    {
        name: "Charlotte",
        wishimg: 'https://genshin.honeyhunterworld.com/img/charlotte_088_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/charlotte_088_gacha_card.webp?x28602',
    },
    {
        name: "Chevreuse",
        wishimg: 'https://genshin.honeyhunterworld.com/img/chevreuse_090_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/chevreuse_090_gacha_card.webp?x28602',
    },
    {
        name: "Chongyun",
        wishimg: 'https://genshin.honeyhunterworld.com/img/chongyun_036_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/chongyun_036_gacha_card.webp?x28602',
    },
    {
        name: "Collei",
        wishimg: 'https://genshin.honeyhunterworld.com/img/collei_067_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/collei_067_gacha_card.webp?x28602',
    },
    {
        name: "Dehya",
        wishimg: 'https://genshin.honeyhunterworld.com/img/dehya_079_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/dehya_079_gacha_card.webp?x28602',
    },
    {
        name: "Diluc",
        wishimg: 'https://genshin.honeyhunterworld.com/img/diluc_016_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/diluc_016_gacha_card.webp?x28602',
    },
    {
        name: "Diona",
        wishimg: 'https://genshin.honeyhunterworld.com/img/diona_039_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/diona_039_gacha_card.webp?x28602',
    },
    {
        name: "Dori",
        wishimg: 'https://genshin.honeyhunterworld.com/img/dori_068_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/dori_068_gacha_card.webp?x28602',
    },
    {
        name: "Faruzan",
        wishimg: 'https://genshin.honeyhunterworld.com/img/faruzan_076_icon_70.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/faruzan_076_gacha_card.webp?x28602',
    },
    {
        name: "Fischl",
        wishimg: 'https://genshin.honeyhunterworld.com/img/fischl_031_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/fischl_031_gacha_card.webp?x28602',

    },
    {
        name: "Freminet",
        wishimg: 'https://genshin.honeyhunterworld.com/img/freminet_085_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/freminet_085_gacha_card.webp?x28602',
    },
    {
        name: "Gaming",
        wishimg: 'https://genshin.honeyhunterworld.com/img/gaming_092_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/gaming_092_gacha_card.webp?x28602',
    },
    {
        name: "Gorou",
        wishimg: 'https://genshin.honeyhunterworld.com/img/gorou_055_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/gorou_055_gacha_card.webp?x28602',
    },
    {
        name: "Jean",
        wishimg: 'https://genshin.honeyhunterworld.com/img/qin_003_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/qin_003_gacha_card.webp?x28602',
    },
    {
        name: "Kaeya",
        wishimg: 'https://genshin.honeyhunterworld.com/img/kaeya_015_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/kaeya_015_gacha_card.webp?x28602',
    },
    {
        name: "Kaveh",
        wishimg: 'https://genshin.honeyhunterworld.com/img/kaveh_081_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/kaveh_081_gacha_card.webp?x28602',
    },
    {
        name: "Keqing",
        wishimg: 'https://genshin.honeyhunterworld.com/img/keqing_042_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/keqing_042_gacha_card.webp?x28602',
    },
    {
        name: "Kirara",
        wishimg: 'https://genshin.honeyhunterworld.com/img/momoka_061_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/momoka_061_gacha_card.webp?x28602',
    },
    {
        name: "Kujou Sara",
        wishimg: 'https://genshin.honeyhunterworld.com/img/sara_056_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/sara_056_gacha_card.webp?x28602',
    },
    {
        name: "Kuki Shinobu",
        wishimg: 'https://genshin.honeyhunterworld.com/img/shinobu_065_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/shinobu_065_gacha_card.webp?x28602',
    },
    {
        name: "Layla",
        wishimg: 'https://genshin.honeyhunterworld.com/img/layla_074_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/layla_074_gacha_card.webp?x28602',
    },
    {
        name: "Lisa",
        wishimg: 'https://genshin.honeyhunterworld.com/img/lisa_006_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/lisa_006_gacha_card.webp?x28602',
    },
    {
        name: "Lynette",
        wishimg: 'https://genshin.honeyhunterworld.com/img/linette_083_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/linette_083_gacha_card.webp?x28602',
    },
    {
        name: "Mika",
        wishimg: 'https://genshin.honeyhunterworld.com/img/mika_080_side_icon_70.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/mika_080_gacha_card.webp?x28602',
    },
    {
        name: "Mona",
        wishimg: 'https://genshin.honeyhunterworld.com/img/mona_041_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/mona_041_gacha_card.webp?x28602',

    },
    {
        name: "Nahida",
        wishimg: 'https://genshin.honeyhunterworld.com/img/nahida_073_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/nahida_073_gacha_card.webp?x28602',
    },
    {
        name: "Ningguang",
        wishimg: 'https://genshin.honeyhunterworld.com/img/ningguang_027_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/ningguang_027_gacha_card.webp?x28602',
    },
    {
        name: "Noelle",
        wishimg: 'https://genshin.honeyhunterworld.com/img/noel_034_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/noel_034_gacha_card.webp?x28602',
    },
    {
        name: "Qiqi",
        wishimg: 'https://genshin.honeyhunterworld.com/img/qiqi_035_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/qiqi_035_gacha_card.webp?x28602',
    },
    {
        name: "Razor",
        wishimg: 'https://genshin.honeyhunterworld.com/img/razor_020_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/razor_020_gacha_card.webp?x28602',
    },
    {
        name: "Rosaria",
        wishimg: 'https://genshin.honeyhunterworld.com/img/rosaria_045_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/rosaria_045_gacha_card.webp?x28602',
    },
    {
        name: "Sayu",
        wishimg: 'https://genshin.honeyhunterworld.com/img/sayu_053_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/sayu_053_gacha_card.webp?x28602',
    },
    {
        name: "Shikanoin Heizou",
        wishimg: 'https://genshin.honeyhunterworld.com/img/heizo_059_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/heizo_059_gacha_card.webp?x28602',
    },
    {
        name: "Sucrose",
        wishimg: 'https://genshin.honeyhunterworld.com/img/sucrose_043_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/sucrose_043_gacha_card.webp?x28602',
    },
    {
        name: "Thoma",
        wishimg: 'https://genshin.honeyhunterworld.com/img/tohma_050_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/tohma_050_gacha_card.webp?x28602',
    },
    {
        name: "Tighnari",
        wishimg: 'https://genshin.honeyhunterworld.com/img/tighnari_069_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/tighnari_069_gacha_card.webp?x28602'
    },
    {
        name: "Xiangling",
        wishimg: 'https://genshin.honeyhunterworld.com/img/xiangling_023_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/xiangling_023_gacha_card.webp?x28602',
    },
    {
        name: "Xingqiu",
        wishimg: 'https://genshin.honeyhunterworld.com/img/xingqiu_025_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/xingqiu_025_gacha_card.webp?x28602',
    },
    {
        name: "Xinyan",
        wishimg: 'https://genshin.honeyhunterworld.com/img/xinyan_044_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/xinyan_044_gacha_card.webp?x28602',
    },
    {
        name: "Yanfei",
        wishimg: 'https://genshin.honeyhunterworld.com/img/feiyan_048_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/feiyan_048_gacha_card.webp?x28602',
    },
    {
        name: "Yaoyao",
        wishimg: 'https://genshin.honeyhunterworld.com/img/yaoyao_077_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/yaoyao_077_gacha_card.webp?x28602',
    },
    {
        name: "Yunjin",
        wishimg: 'https://genshin.honeyhunterworld.com/img/yunjin_064_gacha_splash.webp?x28602',
        cardimg: 'https://genshin.honeyhunterworld.com/img/yunjin_064_gacha_card.webp?x28602x',
    },
    {
        name: "Dragon's Bane",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n13401_gacha_icon.webp?x28602',
    },
    {
        name: "Eye of Perception",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n14409_gacha_icon.webp?x28602',
    },
    {
        name: "Favonius Codex",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n14401_gacha_icon.webp?x28602',
    },
    {
        name: "Favonius Greatsword",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n12401_gacha_icon.webp?x28602',
    },
    {
        name: "Favonius Lance",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n13407_gacha_icon.webp?x28602',
    },
    {
        name: "Favonius Sword",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n11401_gacha_icon.webp?x28602',
    },
    {
        name: "Favonius Warbow",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n15401_gacha_icon.webp?x28602',
    },
    {
        name: "Lion's Roar",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n11405_gacha_icon.webp?x28602',
    },
    {
        name: "Rainslasher",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n12405_gacha_icon.webp?x28602',
    },
    {
        name: "Rust",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n15405_gacha_icon.webp?x28602',
    },
    {
        name: "Sacrificial Bow",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n15403_gacha_icon.webp?x28602',
    },
    {
        name: "Sacraficial Fragments",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n14403_gacha_icon.webp?x28602',
  
    },
    {
        name: "Sacraficial Greatsword",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n12403_gacha_icon.webp?x28602',
    },
    {
        name: "Sacraficial Sword",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n11403_gacha_icon.webp?x28602',
    },
    {
        name: "The Bell",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n12402_gacha_icon.webp?x28602',
    },
    {
        name: "The Flute",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n11402_gacha_icon.webp?x28602',
    },
    {
        name: "The Stringless",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n15402_gacha_icon.webp?x28602',
    },
    {
        name: "The Widsith",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n14402_gacha_icon.webp?x28602',
    },
    {
        name: "Raven Bow",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n15301_gacha_icon.webp?x28602',
    },
    {
        name: "Sharpshooter's Oath",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n15302_gacha_icon.webp?x28602',
    },
    {
        name: "Slingshot",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n15304_gacha_icon.webp?x28602',
    },
    {
        name: "Emerald Orb",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n14304_gacha_icon.webp?x28602',
    },
    {
        name: "Magic Guide",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n14301_gacha_icon.webp?x28602',
    },
    {
        name: "Thrilling Tales of Dragon Slayers",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n14302.webp?x28602',
    },
    {
        name: "Bloodtainted Greatsword",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n12302_gacha_icon.webp?x28602',
    },
    {
        name: "Debate Club",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n12305_gacha_icon.webp?x28602',
    },
    {
        name: "Ferrous Shadow",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n12301_gacha_icon.webp?x28602',
    },
    {
        name: "Black Tassel",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n13303_gacha_icon.webp?x28602',
    },
    {
        name: "Cool Steel",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n11301_gacha_icon.webp?x28602',
    },
    {
        name: "Harbinger of Dawn",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n11302_gacha_icon.webp?x28602',
    },
    {
        name: "Skyrider Sword",
        wishimg: 'https://genshin.honeyhunterworld.com/img/i_n11306_gacha_icon.webp?x28602',
    },
];

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
const wishHistory = ref([]);

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
