<script setup>
import { useRouter } from 'vue-router'

defineProps({
  event: {
    required: true
  },
})

const router = useRouter()

const register = () => {
  // pretend a registration API is called and confirmed
  router.push({
    name: 'event-details'
  })
}
</script>

<template>
  <p>Register for the event here</p>
  <button @click="register">Register me!</button>
</template>
