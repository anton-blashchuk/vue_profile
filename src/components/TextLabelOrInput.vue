<script setup lang="ts">
import { ref } from 'vue'

// Define props with default
const props = withDefaults(defineProps<{
    name: string,
    isEdit?: boolean
}>(),
    {
        isEdit: false
    })

// Local reactive state
const text_value = ref("")
</script>

<template>
    <div class="flex-input">
        <div class="label">{{ name }}</div>
        <div class="label" v-if="isEdit==false">{{ text_value }}</div>
        <input v-model=text_value v-else></input>
    </div>
</template>

<style scoped>
button {
    font-weight: bold;
}

.flex-input {
    display: flex;
    min-width: 200pt;
    padding-top: 2pt;
    padding-bottom: 2pt;
}

.label {
    padding-left: 6pt;
    padding-right: 6pt;
}
</style>