<script setup lang="ts">
import TextLabelOrInput from './TextLabelOrInput.vue'
import { ref } from 'vue'


defineProps<{
  msg: string
}>()

const is_edit = ref(false)
const toggleButtonText = ref("toggle")

</script>

<template>
  <div class="greetings">
    <TextLabelOrInput name="Navn" :isEdit="is_edit"/>
    <TextLabelOrInput name="E-post" :isEdit="is_edit"/>
    <button @click="is_edit=!is_edit">{{ is_edit ? 'Save' : 'Edit' }}</button>
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

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
