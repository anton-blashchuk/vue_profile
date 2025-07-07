<script setup lang="ts">
import TextLabelOrInput from './TextLabelOrInput.vue'
import { ref, reactive } from 'vue'
import { useVuelidate } from '@vuelidate/core'
import { required, email } from '@vuelidate/validators'


const form = reactive({
 username: '',
 email: '',
 avatarUrl: ''
})

const rules = {
  username: { required },
  email: { required, email },
  avatarUrl: {  }

}
const is_edit = ref(false)
const profileModel = ref( {
  username : "name 2",
  email: "email2@abc.com",
  avatarUrl: "https://prioskompetanse.blob.core.windows.net/followupmedia/uploads/446b104a-24e5-4ed6-8428-7ec7853c7e64.jpg"
})

function toggleEdit() {
  if (!is_edit.value) {
    is_edit.value = true
    return
  }
  //procedure of validation and saving

}
</script>

<template>
  <div class=".profile-container">
    <TextLabelOrInput name="Navn" :isEdit="is_edit" v-model="profileModel.username" />
    <TextLabelOrInput name="E-post" :isEdit="is_edit" v-model="profileModel.email" />
    <TextLabelOrInput name="Avatar URL" :isEdit="is_edit" v-model="profileModel.avatarUrl" />

    <img :src="profileModel.avatarUrl" width="200pt" />
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
