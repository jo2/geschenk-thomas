<template>
  <q-page class="row justify-center">
    <q-carousel animated v-model="slide" arrows style="height: 100vh; width: 100%">
      <q-carousel-slide name="1">
        <q-video class="absolute-full" src="https://www.youtube.com/embed/iik25wqIuFo" />
      </q-carousel-slide>

      <q-carousel-slide v-for="s in slides" :name="s.name" :img-src="s.imgSrc" :key="s.name">
        <div class="absolute-bottom custom-caption">
          <div class="text-h2" v-if="s.caption">{{ s.caption }}</div>
          <div class="text-h5" v-if="s.content">{{ s.content }}</div>
        </div>
      </q-carousel-slide>
    </q-carousel>
  </q-page>
</template>

<script setup lang="ts">
/* eslint-disable global-require */
import { ref } from 'vue';

const slide = ref(1);

const slides = [
  {
    name: 2,
    imgSrc: require('src/assets/thomas-am-grill.jpg'),
    caption: 'Herzlichen Glückwunsch!',
    content: 'Du hast es wieder nicht geschafft, den Darwin Award zu gewinnen.',
  },
  {
    name: 3,
    imgSrc: require('src/assets/kronkorken.jpg'),
    content: 'Das möchten wir mit dir Feiern',
  },
  {
    name: 4,
    imgSrc: require('src/assets/mit-helm.jpg'),
    caption: 'Dein Geschenk',
    content: 'Als Belohnung dafür darfst du einen Ausflug zu einem Paintball-Gelände organisieren. Wir freuen uns schon auf die blauen Flecken.',
  },
  {
    name: 5,
    imgSrc: require('src/assets/gruppenfoto.jpg'),
    caption: 'Alles Gute!',
    content: 'Wünschen dir Alex, Christoph, Franka, Jan, Johannes, Jonas, Marius und Sarah.',
  },
  {
    name: 6,
    imgSrc: require('src/assets/bier.jpg'),
    caption: 'Und nun.. Prost!',
  },
  {
    name: 7,
    imgSrc: require('assets/wo-blocker.jpg'),
    caption: 'Achja..',
  },
];

</script>

<style lang="scss">
.custom-caption {
  text-align: center;
  padding: 12px;
  color: white;
  background-color: rgba(0, 0, 0, .3);
  font-family: Impact, sans-serif;
}
</style>
