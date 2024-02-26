<template>
  <header>
    <nav>
        <RouterLink to="/">Wish</RouterLink>
        <RouterLink to="/about">Index</RouterLink>
    </nav>
  </header>
  <RouterView />
</template>

<script setup>
const banners = [
 {
   banner: "VentiA",
   rateupfivestar: "Venti",
   rateupfourstar: ["Barbara", "Fischl", "Xiangling"],
   regfourstars: ["Amber", "Lisa", "Kaeya", "Noelle", "Bennett", "Razor", "Beidou", "Xingqiu", "Chongyun", "Ningguang", "Sucrose", "Favonius Warbow", "Rust", "Sacrificial Bow", "The Stringless", "Favonius Sword", "Lion's Roar", "Sacrificial Sword", "The Flute", "Dragon's Bane", "Favonius Lance", "Sacrificial Greatsword", "The Bell", "Eye of Perception", "Favonius Codex", "Sacrificial Fragments", "The Widsith", "Rainslasher"], 
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/first-genshin-banner-ever-first-venti-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/venti_022_side_icon.webp?x54247'
 },
 {
   banner: "Amos' Bow/Aquila Favonia",
   rateupfivestar: ["Amos' Bow", "Aquila Favonia"],
   rateupfourstar: ["The Bell", "The Flute", "The Widsth", "The Stringless", "Favonius Lance"],
   regfourstars: ["Amber", "Lisa", "Kaeya", "Noelle", "Bennett", "Razor", "Beidou", "Xingqiu", "Chongyun", "Ningguang","Sucrose", "Xiangliang", "Fischl", "Barbara", "Favonius Warbow", "Rust", "The Stringless", "Favonius Sword", "Lion's Roar", "The Flute", "Favonius Lance", "The Bell", "Eye of Perception", "Favonius Codex", "The Widsith", "Rainslasher"], 
   regfivestars: ["Skyward Harp", "Skyward Blade", "Primordial Jade Winged Spear", "Skyward Spine", "Skyward Pride", "Wolf's Gravestone", "Lost Prayer to the Sacred Winds", "Skyward Atlas"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/b/bc/2020-09-28_Epitome_Invocation.png?width=1024',
   sideimg: ''
 },
 {
   banner: "KleeA",
   rateupfivestar: "Klee",
   rateupfourstar: ["Noelle", "Sucrose", "Xingqiu"],
   regfourstars: ["Amber", "Lisa", "Kaeya", "Barbara", "Bennett", "Razor", "Beidou", "Xiangling", "Chongyun", "Ningguang", "Fishcl", "Favonius Warbow", "Rust", "Sacrificial Bow", "The Stringless", "Favonius Sword", "Lion's Roar", "Sacrificial Sword", "The Flute", "Dragon's Bane", "Favonius Lance", "Sacrificial Greatsword", "The Bell", "Eye of Perception", "Favonius Codex", "Sacrificial Fragments", "The Widsith", "Rainslasher"], 
   regfivestars: ["Amos' Bow", "Skyward Harp", "Aquila Favonia", "Skyward Blade", "Primordial Jade Winged Spear", "Skyward Spine", "Skyward Pride", "Wolf's Gravestone", "Lost Prayer to the Sacred Winds", "Skyward Atlas"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/first-klee-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/klee_029_side_icon.webp?x54247'
 },
 {
   banner: "Lost Prayer to the Sacred Winds/Wolf's Gravestone",
   rateupfivestar: ["Lost Prayer to the Sacred Winds", "Wolf's Gravestone"],
   rateupfourstar: ["Sacrificial Greatsword", "Sacrificial Sword", "Sacrificial Fragments", "Sacrificial Bow", "Dragon's Bane"],
   regfourstars: ["Amber", "Lisa", "Kaeya", "Noelle", "Bennett", "Razor", "Beidou", "Xingqiu", "Chongyun", "Ningguang","Sucrose", "Xiangliang", "Fischl", "Barbara", "Favonius Warbow", "Rust", "The Stringless", "Favonius Sword", "Lion's Roar", "The Flute", "Favonius Lance", "The Bell", "Eye of Perception", "Favonius Codex", "The Widsith", "Rainslasher"], 
   regfivestars: ["Amos' Bow", "Skyward Harp", "Aquila Favonia", "Skyward Blade", "Primordial Jade Winged Spear", "Skyward Spine", "Skyward Pride","Skyward Atlas"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/4/4c/2020-10-19_Epitome_Invocation.jpg?width=1024',
   sideimge: ''
 },
 {
   banner: "TartagliaA",
   rateupfivestar: "Tartaglia",
   rateupfourstar: ["Beidou", "Ningguang", "Diona"],
   regfourstars: ["Amber", "Lisa", "Kaeya", "Noelle", "Bennett", "Razor", "Xingqiu", "Chongyun", "Sucrose", "Xiangliang", "Fischl", "Barbara", "Favonius Warbow", "Rust", "The Stringless", "Favonius Sword", "Lion's Roar", "The Flute", "Favonius Lance", "The Bell", "Eye of Perception", "Favonius Codex", "The Widsith", "Rainslasher"], 
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/first-childe-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/tartaglia_033_side_icon.webp?x54247'
 },
 {
   banner: "Skyward Harp/Memory of Dust",
   rateupfivestar: ["Skyward Harp", "Memory of Dust"],
   rateupfourstar: ["Rust", "The Flute", "Favonius Lance", "Rainslasher", "Eye of Perception"],
   regfourstars: ["Amber", "Lisa", "Kaeya", "Noelle", "Bennett", "Razor", "Beidou", "Xingqiu", "Chongyun", "Ningguang","Sucrose", "Xiangliang", "Fischl", "Barbara", "Diona","Favonius Warbow", "Rust", "The Stringless", "Favonius Sword", "Lion's Roar", "The Flute", "Favonius Lance", "The Bell", "Eye of Perception", "Favonius Codex", "The Widsith", "Rainslasher"], 
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/8/8e/2020-11-10_Epitome_Invocation.jpg?width=1024',
   sideimge: '',
 },
 {
   banner: "ZhongliA",
   rateupfivestar: "Zhongli",
   rateupfourstar: ["Chongyun", "Xinyan", "Razor"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/first-zhongli-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/zhongli_030_side_icon.webp?x54247'
 },
 {
   banner: "Vortex Vanquisher/The Unforged",
   rateupfivestar: ["Vortex Vanquisher", "The Unforged"],
   rateupfourstar: ["The Bell", "Lion's Roar", "Favonius Codex", "Favonius Warbow", "Dragon's Bane"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/1/11/2020-12-02_Epitome_Invocation.jpg?width=1024',
   sideimge: ''
 },
 {
   banner: "AlbedoA",
   rateupfivestar: "Albedo",
   rateupfourstar: ["Bennett", "Fischl", "Sucrose"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/first-albedo-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/albedo_038_side_icon.webp?x54247'
 },
 {
   banner: "Summit Shaper/Skyward Atlas",
   rateupfivestar: ["Summit Shaper", "Skyward Atlas"],
   rateupfourstar: ["Sacrificial Fragments", "The Stringless", "Favonius Greatsword", "Favonius Lance", "Favonius Sword"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/5/51/2020-12-23_Epitome_Invocation.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "GanyuA",
   rateupfivestar: "Ganyu",
   rateupfourstar: ["Xiangling", "Noelle", "Xingqiu"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/first-ganyu-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/ganyu_037_side_icon.webp?x54247'
 },
 {
   banner: "Amos' Bow/Skyward Pride",
   rateupfivestar: ["Amos' Bow", "Skyward Pride"],
   rateupfourstar: ["Sacrificial Sword", "Eye of Perception", "The Bell", "Dragon's Bane", "Favonius Warbow"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/4/41/2021-01-13_Epitome_Invocation.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "XiaoA",
   rateupfivestar: "Xiao",
   rateupfourstar: ["Beidou", "Diona", "Xinyan"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/first-xiao-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/xiao_026_side_icon.webp?x54247'
 },
 {
   banner: "Primordial Jade Winged-Spear/Primordial Jade Cutter",
   rateupfivestar: ["Primordial Jade Winged-Spear", "Primordial Jade Cutter"],
   rateupfourstar: ["Eye of Perception", "Rust","Favonius Lance", "The Flute", "Sacrificial Greatsword"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/1/14/2021-02-03_Epitome_Invocation.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "KeqingA",
   rateupfivestar: "Keqing",
   rateupfourstar: ["Barbara", "Bennett", "Ningguang"],
   regfivestars: ["Jean", "Diluc", "Mona", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/keqing-banner-genshin-impact-dance-of-lanterns.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/keqing_042_side_icon.webp?x54247'
 },
 {
   banner: "Wolf's Gravestone/Staff of Homa",
   rateupfivestar: ["Wolf's Gravestone", "Staff of Homa"],
   rateupfourstar: ["Lithic Blade", "Lion's Roar", "Sacrificial Bow", "Lithic Spear", "The Widsith"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/0/03/2021-02-23_EpitomeInvocation.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "HutaoA",
   rateupfivestar: "Hu Tao",
   rateupfourstar: ["Chongyun", "Xiangling", "Xingqiu"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/hu-tao-first-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/hutao_046_side_icon.webp?x54247'
 },
 {
   banner: "VentiB",
   rateupfivestar: "Venti",
   rateupfourstar: ["Noelle", "Razor", "Sucrose"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/venti-first-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/venti_022_side_icon.webp?x54247'
 },
 {
   banner: "Elegy for the End/Skyward Blade",
   rateupfivestar: ["Elegy for the End", "Skyward Blade"],
   rateupfourstar: ["The Alley Flash", "Favonius Greatsword", "Favonius Warbow", "Dragon's Bane", "Wine and Song"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/5/51/2021-03-16_Epitome_Invocation.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "TartagliaB",
   rateupfivestar: "Tartaglia",
   rateupfourstar: ["Rosaria", "Barbara", "Fischl"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/childe-first-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/tartaglia_033_side_icon.webp?x54247'
 },
 {
   banner: "Skyward Harp/Lost Prayers to the Sacred Winds",
   rateupfivestar: ["Skyward Harp", "Lost Prayers to the Sacred Winds"],
   rateupfourstar: ["Alley Hunter", "Sacrificial Greatsword", "Favonius Lance", "Favonius Sword", "Favonius Codex"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/d/da/2021-04-06_EpitomeInvocation.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "ZhongliB",
   rateupfivestar: "Zhongli",
   rateupfourstar: ["Yanfei", "Diona", "Noelle"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/zhongli-first-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/zhongli_030_side_icon.webp?x54247'
 },
 {
   banner: "Summit Shaper/Memory of Dust",
   rateupfivestar: ["Summit Shaper", "Memory of Dust"],
   rateupfourstar: ["Lithic Spear","The Flute", "Eye of Perception", "Sacrificial Bow", "Lithic Blade"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/3/3c/2021-04-28_Epitome_Invocation.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "EulaA",
   rateupfivestar: "Eula",
   rateupfourstar: ["Beidou", "Xingqiu", "Xinyan"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/eula-first-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/eula_051_side_icon.webp?x54247'
 },
 {
   banner: "Aquila Favonia/Song of Broken Pines",
   rateupfivestar: ["Aquila Favonia", "Song of Broken Pines"],
   rateupfourstar: ["Sacrificial Sword", "Rust", "Sacrificial Fragments", "Dragon's Bane", "Rainslasher"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/9/92/Wish_Epitome_Invocation_2021-05-18.png?width=1024',
   sideimg: ''
 },
 {
   banner: "KleeB",
   rateupfivestar: "Klee",
   rateupfourstar: ["Barbara", "Fischl", "Sucrose"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/klee-first-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/klee_029_side_icon.webp?x54247'
 },
 {
   banner: "Lost Prayers of the Sacred Winds, Skyward Pride",
   rateupfivestar: ["Lost Prayers of the Sacred Winds", "Skyward Pride"],
   rateupfourstar: ["Mitternachts Waltz", "The Widsith", "Lion's Roar", "The Bell", "Favonius Lance"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/c/cb/Wish_Epitome_Invocation_2021-06-09.png?width=1024',
   sideimg: ''
 },
 {
   banner: "KazuhaA",
   rateupfivestar: "Kaedehara Kazuha",
   rateupfourstar: ["Bennett", "Razor", "Rosaria"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/kazuha-first-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg:'https://genshin.honeyhunterworld.com/img/kazuha_047_side_icon.webp?x54247'
 },
 {
   banner: "Freedom Sworn/Skyward Atlas",
   rateupfivestar: ["Freedom Sworn", "Skyward Atlas"],
   rateupfourstar: ["The Alley Flash", "Alley Hunter", "Dragon's Bane", "Wine and Song", "Favonius Greatsword"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/1/15/2021_07_03_Epitome_Invocation.png?width=1024',
   sideimg: ''
 },
 {
   banner: "AyakaA",
   rateupfivestar: "Kamisato Ayaka",
   rateupfourstar: ["Chongyun", "Ningguang", "Yanfei"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/ayaka-first-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/ayaka_002_side_icon.webp?x54247'
 },
 {
   banner: "Mistsplitter Reforged/Skyward Spine",
   rateupfivestar: ["Mistsplitter Reforged", "Skyward Spine"],
   rateupfourstar: ["The Stringless", "Favonius Sword","Favonius Codex","Favonius Lance","Sacrificial Greatsword"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/d/d5/2021-07-22_Epitome_Invocation.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "YoimiyaA",
   rateupfivestar: "Yoimiya",
   rateupfourstar: ["Sayu", "Diona", "Xinyan"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/yoimiya-first-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/yoimiya_049_side_icon.webp?x54247'
 },
 {
   banner: "Thundering Pulse/Skyward Blade",
   rateupfivestar: ["Thundering Pulse", "Skyward Blade"],
   rateupfourstar: ["Sacrificial Sword","Favonius Warbow", "Sacrificial Fragments","Dragon's Bane", "Rainslasher"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/a/a8/Wish_Epitome_Invocation_2021-08-10.png?width=1024',
   sideimg: ''
 },
 {
   banner: "RaidenShogunA",
   rateupfivestar: "Raiden Shogun",
   rateupfourstar: ["Kujou Sara", "Sucrose", "Xiangling"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/raiden-shogun-first-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/shougun_052_side_icon.webp?x54247'
 },
 {
   banner: "The Unforged/Engulfing Lightning",
   rateupfivestar: ["The Unforged", "Engulfing Lightning"],
   rateupfourstar: ["Sacrificial Bow","The Widsith","Favonius Lance","The Bell","Lion's Roar"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/4/49/Wish_Epitome_Invocation_2021-09-01.png?width=1024',
   sideimg: ''
 },
 {
   banner: "KokomiA",
   rateupfivestar: "Sangonomiya Kokomi",
   rateupfourstar: ["Beidou", "Rosaria", "Xingqiu"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/kokomi-debut-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/kokomi_054_side_icon.webp?x54247'
 },
 {
   banner: "Primordial Jade Cutter/Everlasting Moonglow",
   rateupfivestar: ["Primordial Jade Cutter", "Everlasting Moonglow"],
   rateupfourstar: ["Favonius Codex","The Flute","The Stringless","Favonius Greatsword","Dragon's Bane"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/1/17/Wish_Epitome_Invocation_2021-09-21.png?width=1024',
   sideimg: ''
 },
 {
   banner: "TartagliaC",
   rateupfivestar: "Tartaglia",
   rateupfourstar: ["Chongyun", "Ningguang", "Yanfei"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/childe-second-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/tartaglia_033_side_icon.webp?x54247'
 },
 {
   banner: "Polar Star/Memory of Dust",
   rateupfivestar: ["Polar Star", "Memory of Dust"],
   rateupfourstar: ["Akuoumaru", "Rust", "Favonius Sword", "Eye of Perception", "Favonius Lance"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/1/13/Genshin-impact-weapon-banner-polar-memory.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "HutaoB",
   rateupfivestar: "Hu Tao",
   rateupfourstar: ["Thoma", "Sayu", "Diona"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/hu-tao-first-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/hutao_046_side_icon.webp?x54247'
 },
 {
   banner: "Staff of Homa/Elegy for the End",
   rateupfivestar: ["Staff of Homa", "Elegy for the End"],
   rateupfourstar: ["Wavebreaker's Fin", "Mouun's Moon", "Sacrificial Sword", "The Widsith", "Rainslasher"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/b/b8/Genshin-impact-weapon-banner-elegy-homa.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "EulaB",
   rateupfivestar: "Eula",
   rateupfourstar: ["Bennett", "Rosaria", "Noelle"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/eula-first-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/eula_051_side_icon.webp?x54247',
 },
 {
   banner: "AlbedoB",
   rateupfivestar: "Albedo",
   rateupfourstar: ["Bennett", "Rosaria", "Noelle"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/albedo-first-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimge: 'https://genshin.honeyhunterworld.com/img/albedo_038_side_icon.webp?x54247'
 },
 {
   banner: "Freedom Sworn/Song of Broken Pines",
   rateupfivestar: ["Freedom Sworn", "Song of Broken Pines"],
   rateupfourstar: ["Wine and Song", "Lion's Roar", "Dragon's Bane,","Sacrificial Greatsword", "Alley Hunter"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/b/b4/Genshin-impact-weapon-banner-freedom-song.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "IttoA",
   rateupfivestar: "Arataki Itto",
   rateupfourstar: ["Gorou", "Barbara", "Xiangling"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/itto-first-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/itto_057_side_icon.webp?x54247'
 },
 {
   banner: "Skyward Harp/Redhorn Stonethresher",
   rateupfivestar: ["Skyward Harp", "Redhorn Stonethresher"],
   rateupfourstar: ["Mitternacht Waltz", "The Alley Flash", "Sacrifical Fragments", "The Bell", "Favonius Lance"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/1/14/Genshin-impact-weapon-banner-skyward-redhorn.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "ShenheA",
   rateupfivestar: "Shenhe",
   rateupfourstar: ["Chongyun", "Ningguang", "Yunjin"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/shenhe-debut-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/shenhe_063_side_icon.webp?x54247'
 },
 {
   banner: "XiaoB",
   rateupfivestar: "Xiao",
   rateupfourstar: ["Chongyun", "Ningguang", "Yunjin"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/xiao-first-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/xiao_026_side_icon.webp?x54247'
 },
 {
   banner: "Calamity Queller/Primordial Jade Winged-Spear",
   rateupfivestar: ["Calamity Queller", "Primordial Jade Winged-Spear"],
   rateupfourstar: ["Favonius Warbow", "The Flute", "Lithic Spear", "Favonius Greatsword", "The Widsith"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/6/63/Genshin-impact-weapon-banner-calamity-jade.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "ZhongliC",
   rateupfivestar: "Zhongli",
   rateupfourstar: ["Xingqiu", "Beidou", "Yanfei"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/zhongli-second-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/zhongli_030_side_icon.webp?x54247'
 },
 {
   banner: "GanyuB",
   rateupfivestar: "Ganyu",
   rateupfourstar: ["Xingqiu", "Beidou", "Yanfei"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/ganyu-first-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/ganyu_037_side_icon.webp?x54247'
 },
 {
   banner: "Vortex Vanquisher/Amos' Bow",
   rateupfivestar: ["Vortex Vanquisher", "Amos' Bow"],
   rateupfourstar: ["Dragon's Bane", "Lithic Blade", "Favonius Sword", "Favonius Codex", "Sacrificial Bow"],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/2/2c/Genshin-impact-weapon-banner-vortex-amos.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "YaeMikoA",
   rateupfivestar: "Yae Miko",
   rateupfourstar: ["Thoma", "Fischl", "Diona"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/yae-miko-first-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/yae_058_side_icon.webp?x54247'
 },
 {
   banner: "Kagura's Verity/Primordial Jade Cutter",
   rateupfivestar: ["Kagura's Verity", "Primordial Jade Cutter"],
   rateupfourstar: [""],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/e/eb/Genshin-impact-weapon-banner-kagura-jade.jpeg?width=1024',
   sideimg: ''
 },
 {
   banner: "RaidenShogunB",
   rateupfivestar: "Raiden Shogun",
   rateupfourstar: ["Bennett", "Kujou Sara", "Xinyan"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/raiden-shogun-first-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/shougun_052_side_icon.webp?x54247'
 },
 {
   banner: "KokomiB",
   rateupfivestar: "Sangonomiya Kokomi",
   rateupfourstar: ["Bennett", "Kujou Sara", "Xinyan"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/kokomi-first-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/kokomi_054_side_icon.webp?x54247'
 },
 {
   banner: "Everlasting Moonglow/Engulfing Lightning",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/f/f6/Genshin-impact-weapon-banner-engulfing-everlasting.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "AyatoA",
   rateupfivestar: "Kamisato Ayato",
   rateupfourstar: ["Sucrose", "Xiangling", "Yunjin"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/ayato-first-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/ayato_066_side_icon.webp?x54247'
 },
 {
   banner: "VentiC",
   rateupfivestar: "Venti",
   rateupfourstar: ["Sucrose", "Xiangling", "Yunjin"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/venti-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/venti_022_side_icon.webp?x54247'
 },
 {
   banner: "Haran Geppaku Futsu/Elegy for the End ",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/e/ed/Genshin-impact-weapon-banner-haran-elegy.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "AyakaB",
   rateupfivestar: "Kamisato Ayaka",
   rateupfourstar: ["Razor", "Rosaria", "Sayu"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/ayaka-first-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/ayaka_002_side_icon.webp?x54247'
 },
 {
   banner: "Mistsplitter Reforged/The Unforged",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/c/c7/Genshin-impact-weapon-banner-mistsplitter-unforged.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "XiaoC",
   rateupfivestar: "Xiao",
   rateupfourstar: ["Yanfei", "Barbara", "Noelle"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/xiao-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/xiao_026_side_icon.webp?x54247'
 },
 {
   banner: "YelanA",
   rateupfivestar: "Yelan",
   rateupfourstar: ["Yanfei", "Barbara", "Noelle"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/yelan-first-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/yelan_060_side_icon.webp?x54247'
 },
 {
   banner: "Aqua Simulacra/Primordial Jade Winged Spear",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/a/a1/Weapon_Banner_Simulcra_Jade_Winged_Spear.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "IttoB",
   rateupfivestar: "Arataki Itto",
   rateupfourstar: ["Kuki Shinobu", "Gorou", "Chongyun"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/itto-first-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/itto_057_side_icon.webp?x54247'
 },
 {
   banner: "Redhorn Stonetresher/Memory of Dust",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/7/71/Weapon_Banner_Redhorn_Stonethresher%2C_Memory_of_Dust.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "KleeC",
   rateupfivestar: "Klee",
   rateupfourstar: ["Shikanoin Heizou","Thoma", "Ningguang"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/klee-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/klee_029_side_icon.webp?x54247'
 },
 {
   banner: "KazuhaB",
   rateupfivestar: "Kaedehara Kazuha",
   rateupfourstar: ["Shikanoin Heizou","Thoma", "Ningguang"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/kazuha-first-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/kazuha_047_side_icon.webp?x54247'
 },
 {
   banner: "Freedom Sworn/Lost Prayer to the Sacred Winds",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/6/6c/Weapon_Banner_Freedom_Sworn_and_Lost_Prayer_to_the_Sacred_Winds.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "YoimiyaB",
   rateupfivestar: "Yoimiya",
   rateupfourstar: ["Yunjin", "Xinyan", "Bennett"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/yoimiya-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/yoimiya_049_side_icon.webp?x54247'
 },
 {
   banner: "Thundering Pulse/Summit Shaper",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/5/51/Thundering_Pulse_2.8_Banner.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "ZhongliD",
   rateupfivestar: "Zhongli",
   rateupfourstar: ["Collei", "Diona", "Fischl"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/zhongli-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/zhongli_030_side_icon.webp?x54247'
 },
 {
   banner: "TighnariA",
   rateupfivestar: "Tighnari",
   rateupfourstar: ["Collei", "Diona", "Fischl"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/tighnari-banner-genshin-impact.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/tighnari_069_side_icon.webp?x54247'
 },
 {
   banner: "Hunter's Path/Vortex Vanquisher",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/c/cb/Hunter%27s_Path_and_Vortex_Vanquisher_Aug_-_Sep_2022.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "GanyuC",
   rateupfivestar: "Ganyu",
   rateupfourstar: ["Dori", "Xingqiu", "Surcose"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/ganyu-second-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/ganyu_037_side_icon.webp?x54247'
 },
 {
   banner: "KokomiC",
   rateupfivestar: "Sangonomiya Kokomi",
   rateupfourstar: ["Dori", "Xingqiu", "Surcose"],
   regfivestars: ["Jean", "Diluc", "Mona", "Keqing", "Qiqi"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/kokomi-second-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/kokomi_054_side_icon.webp?x54247'
 },
 {
   banner: "Amos' Bow/Everlasting Moonglow",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/5/59/Amos_Bow_and_Everlasting_Moonglow_Weapon_Banner_September_2022.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "CynoA",
   rateupfivestar: "Cyno",
   rateupfourstar: ["Candace", "Kuki Shinobu", "Sayu"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   regfourstars: [],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/cyno-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/cyno_071_side_icon.webp?x54247'
 },
 {
   banner: "VentiD",
   rateupfivestar: "Venti",
   rateupfourstar: ["Candace", "Kuki Shinobu", "Sayu"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/venti-third-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/venti_022_side_icon.webp?x54247'
 },
 {
   banner: "Elegy for the End/Staff of the Scarlet Sands",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/8/8f/Elegy_and_Staff_of_the_Scarlet_Banner_September_2022.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "AlbedoC",
   rateupfivestar: "Albedo",
   rateupfourstar: ["Barbara", "Beidou", "Xiangling"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/albedo-second-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/albedo_038_side_icon.webp?x54247'
 },
 {
   banner: "NilouA",
   rateupfivestar: "Nilou",
   rateupfourstar: ["Barbara", "Beidou", "Xiangling"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/nilou-first-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/nilou_070_side_icon.webp?x54247'
 },
 {
   banner: "Key of Khaj Nisut/Primordial Jade Cutter",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/6/63/Genshin-weapon-banner-oct-22.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "YoimiyaC",
   rateupfivestar: "Yoimiya",
   rateupfourstar: ["Bennett", "Razor", "Noelle"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/yoimiya-second-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/yoimiya_049_side_icon.webp?x54247'
 },
 {
   banner: "NahidaA",
   rateupfivestar: "Nahida",
   rateupfourstar: ["Bennett", "Razor", "Noelle"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/nahida-first-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/nahida_073_side_icon.webp?x54247'
 },
 {
   banner: "Thundering Pulse/A Thousand Floating Dreams",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/9/9c/Thundering_Pulse_and_Dreams_Banner_2022.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "YaeMikoB",
   rateupfivestar: "Yae Miko",
   rateupfourstar: ["Layla", "Thoma", "Shikanoin Heizou"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/yae-miko-first-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/yae_058_side_icon.webp?x54247'
 },
 {
   banner: "TartagliaD",
   rateupfivestar: "Tartaglia",
   rateupfourstar: ["Layla", "Thoma", "Shikanoin Heizou"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/childe-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/tartaglia_033_side_icon.webp?x54247'
 },
 {
   banner: "Kagura's Verity/Polar Star",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/3/30/Version_3.2_Weapon_Banner_Late_November.png?width=1024',
   sideimg: ''
 },
 {
   banner: "IttoC",
   rateupfivestar: "Arataki Itto",
   rateupfourstar: ["Faruzan", "Gorou", "Yanfei"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg:'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/itto-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/itto_057_side_icon.webp?x54247'
 },
 {
   banner: "WandererA",
   rateupfivestar: "Wanderer",
   rateupfourstar: ["Faruzan", "Gorou", "Yanfei"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/wanderer-first-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/wanderer_075_side_icon.webp?x54247'
 },
 {
   banner: "Tulaytullah's Remembrance/Redhorn Stonethresher",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/c/c0/Version_3.3_Weapon_Banner_Early_December.png?width=1024',
   sideimg: ''
 },
 {
   banner: "AyatoB",
   rateupfivestar: "Kamisato Ayato",
   rateupfourstar: ["Kujou Sara", "Sayu", "Rosaria"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/ayato-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/ayato_066_side_icon.webp?x54247'
 },
 {
   banner: "RaidenShogunC",
   rateupfivestar: "Raiden Shogun",
   rateupfourstar: ["Kujou Sara", "Sayu", "Rosaria"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/raiden-shogun-second-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/shougun_052_side_icon.webp?x54247'
 },
 {
   banner: "Haran Geppaku Futsu/Engulfing Lightning",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/c/cd/3.3_Event_Weapon_Banner_December.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "XiaoD",
   rateupfivestar: "Xiao",
   rateupfourstar: ["YaoYao", "Xinyan", "Yunjin"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/xiao-banner-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/xiao_026_side_icon.webp?x54247'
 },
 {
   banner: "AlhaithamA",
   rateupfivestar: "Alhaitham",
   rateupfourstar: ["YaoYao", "Xinyan", "Yunjin"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/alhaitham-first-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/alhatham_078_side_icon.webp?x54247'
 },
 {
   banner: "Light of Foliar Incision/Primordial Jade Winged Spear",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/4/4d/3.4_Event_Weapon_Banner_Early_February.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "YelanB",
   rateupfivestar: "Yelan",
   rateupfourstar: ["Beidou", "Ningguang", "Xingqiu"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/yelan-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/yelan_060_side_icon.webp?x54247'
 },
 {
   banner: "HutaoC",
   rateupfivestar: "Hu Tao",
   rateupfourstar: ["Beidou", "Ningguang", "Xingqiu"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/hu-tao-rerun-banner-2.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/hutao_046_side_icon.webp?x54247'
 },
 {
   banner: "Aqua Simulacra/Staff of Homa",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/b/b5/3.4_Event_Weapon_Banner_Late_February.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "CynoB",
   rateupfivestar: "Cyno",
   rateupfourstar: ["Bennett", "Collei", "Barbara"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/cyno-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/cyno_071_side_icon.webp?x54247'
 },
 {
   banner: "DehyaA",
   rateupfivestar: "Dehya",
   rateupfourstar: ["Bennett", "Collei", "Barbara"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/dehya-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/dehya_079_side_icon.webp?x54247'
 },
 {
   banner: "Staff of the Scarlet Sands/Beacon of the Reed Sea",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/b/bb/3.5_Stage_I_Weapon_Banner.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "AyakaC",
   rateupfivestar: "Kamisato Ayaka",
   rateupfourstar: ["Mika", "Sucrose", "Diona"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/ayaka-banner-3-5.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/ayaka_002_side_icon.webp?x54247'
 },
 {
   banner: "ShenheB",
   rateupfivestar: "Shenhe",
   rateupfourstar: ["Mika", "Sucrose", "Diona"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/shenhe-banner-3-5.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/shenhe_063_side_icon.webp?x54247'
 },
 {
   banner: "Mistsplitter Reforged/Calamity Queller",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/1/1c/3.5_Stage_II_Weapon_Banner.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "NilouB",
   rateupfivestar: "Nilou",
   rateupfourstar: ["Kuki Shinobu", "Layla", "Dori"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/nilou-event-wish.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/nilou_070_side_icon.webp?x54247'
 },
 {
   banner: "NahidaB",
   rateupfivestar: "Nahida",
   rateupfourstar: ["Kuki Shinobu", "Layla", "Dori"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/nahida-rerun-event-wish.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/nahida_073_side_icon.webp?x54247'
 },
 {
   banner: "Key of Khaj Nisut/A Thousand Floating Dreams",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/2/2e/3.6_Weapon_Banner.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "BaizhuA",
   rateupfivestar: "Baizhu",
   rateupfourstar: ["Kaveh", "Candace", "Fishcl"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   regfourstars: [],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/baizhu-event-wish.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/baizhuer_082_side_icon.webp?x54247'
 },
 {
   banner: "GanyuD",
   rateupfivestar: "Ganyu",
   rateupfourstar: ["Kaveh", "Candace", "Fishcl"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/ganyu-event-wish-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/ganyu_037_side_icon.webp?x54247'
 },
 {
   banner: "Amos' Bow/Jadefall's Splendor",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/6/62/3.6_Weapon_Banner_Phase_2.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "YaeMikoC",
   rateupfivestar: "Yae Miko",
   rateupfourstar: ["Kirara", "Yunjin", "Chongyun"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/yae-miko-banner-genshin-impact.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/yae_058_side_icon.webp?x54247'
 },
 {
   banner: "YoimiyaD",
   rateupfivestar: "Yoimiya",
   rateupfourstar: ["Kirara", "Yunjin", "Chongyun"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/05/yoimiya-banner-genshin-impact.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/yoimiya_049_side_icon.webp?x54247'
 },
 {
   banner: "Thundering Pulse/Kagura's Verity",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/a/a0/3.7_Phase_1_Weapon_Banner.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "AlhaithamB",
   rateupfivestar: "Alhaitham",
   rateupfourstar: ["YaoYao", "Shikanoin Heizou", "Xiangling"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/alhaitham-first-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/alhatham_078_side_icon.webp?x54247'
 },
 {
   banner: "KazuhaC",
   rateupfivestar: "Kaedehara Kazuha",
   rateupfourstar: ["YaoYao", "Shikanoin Heizou", "Xiangling"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/06/kazuha-second-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/kazuha_047_side_icon.webp?x54247'
 },
 {
   banner: "Freedom Sworn/Light of Foliar Incision",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/c/c0/3.7_Phase_2_Weapon_Banner.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "KleeD",
   rateupfivestar: "Klee",
   rateupfourstar: ["Mika", "Thoma", "Razor"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/07/klee-third-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/klee_029_side_icon.webp?x54247'
 },
 {
   banner: "EulaC",
   rateupfivestar: "Eula",
   rateupfourstar: ["Mika", "Thoma", "Razor"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/07/eula-second-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/eula_051_side_icon.webp?x54247'
 },
 {
   banner: "Song of Broken Pines/Lost Prayer to the Sacred Winds",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/b/b8/3.8_Phase_1_Weapon_Banner.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "WandererB",
   rateupfivestar: "Wanderer",
   rateupfourstar: ["Faruzan", "Rosaria", "Yanfei"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/07/scaramouche-wanderer-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/wanderer_075_side_icon.webp?x54247'
 },
 {
   banner: "KokomiD",
   rateupfivestar: "Sangonomiya Kokomi",
   rateupfourstar: ["Faruzan", "Rosaria", "Yanfei"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/07/kokomi-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/kokomi_054_side_icon.webp?x54247'
 },
 {
   banner: "Everlasting Moonglow/Tulaytullah's Remembrance",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/1/13/3.8_Phase_2_Weapon_Banner.jpg?width=1024',
   sideimg: ''
 },
 {
   banner: "YelanC",
   rateupfivestar: "Yelan",
   rateupfourstar: ["Lynette", "Bennett", "Barbara"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/08/yelan-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/yelan_060_side_icon.webp?x54247'
 },
 {
   banner: "LyneyA",
   rateupfivestar: "Lyney",
   rateupfourstar: ["Lynette", "Bennett", "Barbara"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/08/lyney-first-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/liney_084_side_icon.webp?x54247'
 },
 {
   banner: "The First Great Magic/Aqua Simulacra",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://genshin.global/wp-content/uploads/2023/08/epitome-invocation-great-magic-aqua-simulacra.webp',
   sideimg: ''
 },
 {
   banner: "TartagliaE",
   rateupfivestar: "Tartaglia",
   rateupfourstar: ["Freminet", "Sayu", "Noelle"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/09/childe-fourth-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/tartaglia_033_side_icon.webp?x54247'
 },
 {
   banner: "ZhongliE",
   rateupfivestar: "Zhongli",
   rateupfourstar: ["Freminet", "Sayu", "Noelle"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/09/zhongli-fourth-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/zhongli_030_side_icon.webp?x54247'
 },
 {
   banner: "Vortex Vanquisher/Polar Star",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/1/1e/Version_4.0_Phase_2_Weapons.png?width=1024',
   sideimg: ''
 },
 {
   banner: "HutaoD",
   rateupfivestar: "Hu Tao",
   rateupfourstar: ["Xingqiu", "Fishcl", "Diona"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/09/hu-tao-banner-2023-october.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/hutao_046_side_icon.webp?x54247'
 },
 {
   banner: "NeuvilletteA",
   rateupfivestar: "Neuvilette",
   rateupfourstar: ["Xingqiu", "Fishcl", "Diona"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/09/neuvillette-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/neuvillette_087_side_icon.webp?x54247'
 },
 {
   banner: "Staff of Homa/Tome of the Eternal Flow",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/9/99/4.1_Phase_1_Weapon_Banner.png?width=1024',
   sideimg: ''
 },
 {
   banner: "VentiE",
   rateupfivestar: "Venti",
   rateupfourstar: ["Thoma", "Chongyun", "Dori"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/10/venti-rerun-4-1-1.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/venti_022_side_icon.webp?x54247'
 },
 {
   banner: "WriothesleyA",
   rateupfivestar: "Wriothesley",
   rateupfourstar: ["Thoma", "Chongyun", "Dori"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/10/wriothesley-first-banner-1.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/wriothesley_086_side_icon.webp?x54247'
 },
 {
   banner: "Elegy for the End/Cashflow Supervision",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/9/96/4.1_Phase_2_Weapon_Banner.png?width=1024',
   sideimg: ''
 },
 {
   banner: "BaizhuB",
   rateupfivestar: "Baizhu",
   rateupfourstar: ["Charlotte", "Beidou", "Collei"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/11/baizhu-rerun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/baizhuer_082_side_icon.webp?x54247'
 },
 {
   banner: "FurinaA",
   rateupfivestar: "Furina",
   rateupfourstar: ["Charlotte", "Beidou", "Collei"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/11/furina-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/furina_089_side_icon.webp?x54247'
 },
 {
   banner: "Splendor of Tranquil Waters/Jadefall's Splendor",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/6/6c/Genshin_Weapon_Banner_4.2_Phase_1.png?width=1024',
   sideimg: ''
 },
 {
   banner: "AyatoC",
   rateupfivestar: "Ayato",
   rateupfourstar: ["Kirara", "Xiangling", "Kuki Shinobu"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/11/ayato-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/ayato_066_side_icon.webp?x54247'
 },
 {
   banner: "CynoC",
   rateupfivestar: "Cyno",
   rateupfourstar: ["Kirara", "Xiangling", "Kuki Shinobu"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/11/cyno-rerun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/cyno_071_side_icon.webp?x5424'
 },
 {
   banner: "Haran Geppaku Futsu/Staff of the Scarlet Sands",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/9/9c/Genshin_4.2_Phase_2_Weapon_Banner.png?width=1024',
   sideimg: ''
 },
 {
   banner: "AyakaD",
   rateupfivestar: "Kamisato Ayaka",
   rateupfourstar: ["Sucrose", "Candace", "Rosaria"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/12/ayaka-rerun-4-3.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/ayaka_002_side_icon.webp?x54247'
 },
 {
   banner: "NaviaA",
   rateupfivestar: "Navia",
   rateupfourstar: ["Sucrose", "Candace", "Rosaria"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2023/12/in-the-name-of-the-rosula.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/navia_091_side_icon.webp?x54247'
 },
 {
   banner: "Verdict/Mistsplitter Reforged",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://genshin.global/wp-content/uploads/2023/12/genshin-banner-epitome-invocation-verdict.webp',
   sideimg: ''
 },
 {
   banner: "YoimiyaE",
   rateupfivestar: "Yoimiya",
   rateupfourstar: ["Chevreuse","Bennett", "Kujou Sara"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2024/01/tapestry-of-golden-flames-yoimiya.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/yoimiya_049_side_icon.webp?x54247'
 },
 {
   banner: "RaidenShogunD",
   rateupfivestar: "Raiden Shogun",
   rateupfourstar: ["Chevreuse","Bennett", "Kujou Sara"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2024/01/reign-of-serenity-raiden-shogun.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/shougun_052_side_icon.webp?x54247'
 },
 {
   banner: "Thundering Pulse/Engulfing Lightning",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/a/a0/4.3_Phase_2_Weapons.png?width=1024',
   sideimg: ''
 },
 {
   banner: "NahidaC",
   rateupfivestar: "Nahida",
   rateupfourstar: ["Gaming", "Faruzan", "Noelle"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2024/01/nahida-rerun-4-4.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/nahida_073_side_icon.webp?x54247'
 },
 {
   banner: "XianyunA",
   rateupfivestar: "Xianyun",
   rateupfourstar: ["Gaming", "Faruzan", "Noelle"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: 'https://static0.gamerantimages.com/wordpress/wp-content/uploads/2024/01/xianyun-banner.jpg?q=50&fit=crop&w=1500&dpr=1.5',
   sideimg: 'https://genshin.honeyhunterworld.com/img/liuyun_093_side_icon.webp?x54247'
 },
 {
   banner: "A Thousand Floating Dreams/Crane's Echoing Call",
   rateupfivestar: [],
   rateupfourstar: [],
   bannerimg: 'https://oyster.ignimgs.com/mediawiki/apis.ign.com/genshin-impact/5/52/4.4_Phase_1_Weapon_Banner.png?width=1024',
   sideimg: ''
 },
 {
   banner: "YaeMikoD",
   rateupfivestar: "Yae Miko",
   rateupfourstar: ["YaoYao", "Xinyan", "Ningguang"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: null,
   sideimg: 'https://genshin.honeyhunterworld.com/img/yae_058_side_icon.webp?x54247'
 },
 {
   banner: "XiaoE",
   rateupfivestar: "Xiao",
   rateupfourstar: ["YaoYao", "Xinyan", "Ningguang"],
   regfivestars: ["Jean", "Diluc", "Qiqi", "Mona", "Keqing", "Tignari", "Dehya"],
   bannerimg: null,
   sideimg: 'https://genshin.honeyhunterworld.com/img/xiao_026_side_icon.webp?x54247'
 },
 {
   banner: "Kagura's Verity/Primordial Jade Winged Spear",
   rateupfivestar: null,
   rateupfourstar: null,
   bannerimg: null,
   sideimg: ''
 },
]

</script>

<style scoped>
header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  nav {
    text-align: center;
    margin-left: -1rem;
    font-size: 1rem;
    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
