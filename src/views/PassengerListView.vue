<script setup lang="ts">
import PassengerCard from '@/components/PassengerCard.vue'
import type { Passenger } from '@/types'
import { ref, onMounted } from 'vue'
import PassengerService from '@/services/PassengerService'

const passengers = ref<Passenger[]>([])

onMounted(() => {
  PassengerService.getEvents()

    .then((response) => {
      console.log(response)
      passengers.value = response.data.data
    })
    .catch((error) => {
      console.error('There was an error!', error)
    })
})
</script>

<template>
  <h1>Passenger Information</h1>
  <div class="passengers">
    <PassengerCard v-for="passenger in passengers" :key="passenger._id" :passenger="passenger" />
  </div>
</template>

<style scoped>
.passengers {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
