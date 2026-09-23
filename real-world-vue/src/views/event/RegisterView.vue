<script setup>
import { inject } from 'vue'
import { useRouter } from 'vue-router'

const props = defineProps({
  event: {
    required: true
  },
})

const router = useRouter()
const GStore = inject('GStore')

const register = () => {
  // pretend a registration API is called and confirmed
  GStore.flashMessage = `You are successfully registered for ${props.event.title}`
  setTimeout(() => {
    GStore.flashMessage = ''
  }, 3000)
  router.push({
    name: 'event-details'
  })

}
</script>

<template>
  <p>Register for the event here</p>
  <button @click="register">Register me!</button>
</template>
