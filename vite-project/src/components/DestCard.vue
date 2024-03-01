<template>
  <div class="card">
    <div class = "backgroundimgcolor">
      <img :src="Destination.profileimg" alt="" />
    </div>
    <h2>•---------•</h2>
    <h2>{{ Destination.name }}</h2>
  </div>
</template>

<script setup>
const props = defineProps({
  Destination: Object,
});

</script>

<style scoped>
img {
  width: 150px;
  height: 150px;
}

.card {
  height: 240px;
  width: 200px;
  border-radius: 12px;
  padding: 2%;
  margin: 0.5rem 0.5rem;
  background-color: #708090;
  display: flex;
  flex-direction: column;
  text-align: center;
  filter: grayscale(100%);
}

.backgroundimgcolor {
  background-color: #77669c;
/*   #a0652e
#567697 */
  border-radius: 12px;
}

</style>
