<!-- eslint-disable @typescript-eslint/on-unused-vars -->
<script setup lang="ts">
import { toRefs } from 'vue'
import type { Event } from '@/types'
import { useRouter } from 'vue-router'

const props = defineProps<{
  event: Event
  id: String
}>()
const { event } = toRefs(props)
const router = useRouter()
const register = () => {
  router.push({ name: 'event-detail-view' })
}
</script>
<template>
  <p>Register event here</p>
  <button @click="register"></button>
</template>
