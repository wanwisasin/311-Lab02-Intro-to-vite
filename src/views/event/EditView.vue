<script setup lang="ts">
import { toRefs } from 'vue'
import type { Event } from '@/types'

const props = defineProps<{
  event: Event
  id: String
}>()
const { event } = toRefs(props)
</script>
<template>
  <p>Edit event herr</p>
</template>
