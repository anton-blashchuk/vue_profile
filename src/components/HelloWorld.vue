<script setup lang="ts">
import TextLabelOrInput from './TextLabelOrInput.vue'
import { ref } from 'vue'


defineProps<{
  msg: string
}>()

const is_edit = ref(false)
const username = ref('name surname')
const email = ref('email@email.com')
const avatarUrl = ref('https://pixy.org/src/31/thumbs350/315160.jpg')


</script>

<template>
  <div class=".profile-container">
    <TextLabelOrInput name="Navn" :isEdit="is_edit" v-model="username" />
    <TextLabelOrInput name="E-post" :isEdit="is_edit" v-model="email" />
    <TextLabelOrInput name="Avatar URL" :isEdit="is_edit" v-model="avatarUrl" />

    <img :src="avatarUrl" width="200pt" />
    <button @click="is_edit = !is_edit">{{ is_edit ? 'Save' : 'Edit' }}</button>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.profile-container {
  display: flex;
  align-items: center;
  justify-content: center;
  align-self: center;
  justify-self: center;
  justify-items: center;
}

@media (min-width: 1024px) {

  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
