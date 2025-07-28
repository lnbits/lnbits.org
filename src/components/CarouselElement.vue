<template>
  <q-carousel
    animated
    v-model="slide"
    arrows
    swipeable
    navigation
    infinite
    autoplay
    control-color="white"
    transition-prev="slide-right"
    transition-next="slide-left"
    height="450px"
  >
    <q-carousel-slide
      v-for="_slide in slideInfo"
      :key="_slide.name"
      :name="_slide.name"
      :img-src="_slide.image"
      class="q-pa-none"
    >
      <div class="bg-overlay column no-wrap flex-center text-white full-width full-height">
        <div class="text-h2 text-weight-bold q-mb-md">
          {{ _slide.title }}
        </div>
        <div class="text-h4 q-mt-md text-center" style="width: 90%; max-width: 768px">
          {{ _slide.description }}
        </div>
      </div>
    </q-carousel-slide>
  </q-carousel>
</template>

<script setup>
import { ref } from 'vue'

const slide = ref('1')
const slideInfo = [
  {
    name: '1',
    title: 'Accept Bitcoin & Lightning Instantly',
    description:
      'Grow your business by accepting borderless payments with no middlemen, no chargebacks, and instant settlement.',
    image: 'https://cdn.quasar.dev/img/mountains.jpg',
  },
  {
    name: '2',
    title: 'Open Source. Merchant Friendly.',
    description:
      'LNbits is free, open-source, and privacy-first. No sign-up required. Trusted by merchants worldwide.',
    image: 'https://cdn.quasar.dev/img/parallax1.jpg',
  },
  {
    name: '3',
    title: 'Modular & Flexible',
    description:
      'Add powerful extensions like PoS, Invoicing, and Inventory. Customize LNbits to fit your business needs—online or offline.',
    image: 'https://lnbits.com/assets/images/hero/bitcoin-extensions.png',
  },
]
</script>

<style scoped>
.bg-overlay {
  background: rgba(0, 0, 0, 0.5);
}
</style>
