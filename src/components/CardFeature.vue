<template>
  <q-card class="full-width no-shadow">
    <q-card-section v-if="icon">
      <div class="text-h3 text-weight-bolder text-center">
        <q-icon :name="icon"></q-icon>
      </div>
    </q-card-section>
    <q-separator />
    <q-card-section>
      <div class="text-h6 text-center">
        {{ title }}
      </div>
    </q-card-section>
    <q-card-section>
      <div class="text-body1 text-center">
        {{ description }}
      </div>
    </q-card-section>
  </q-card>
</template>

<script setup>
defineProps({
  icon: {
    type: String,
    default: null,
  },
  title: {
    type: String,
    default: 'Feature',
  },
  description: {
    type: String,
    default: 'This is a feature description.',
  },
})
</script>
