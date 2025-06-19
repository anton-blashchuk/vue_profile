<script setup lang="ts">
import { ref } from 'vue'

// Define props with default
const props = withDefaults(defineProps<{
    name: string,
    isEdit?: boolean,
    modelValue: string

}>(),
    {
        isEdit: false
    })

const emit = defineEmits(['update:modelValue'])

function updateValue(event: Event) {
  const target = event.target as HTMLInputElement
  emit('update:modelValue', target.value)
}
// Local reactive state
</script>

<template>
    <div class="flex-input">
        <div class="label">{{ name }}</div>
        <div class="input-or-value" v-if="isEdit==false">{{ modelValue }}</div>
        <input class="input-or-value"  :value="modelValue" @input="updateValue" v-else>
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
    border: solid;
    border-width: 1pt;
    border-color: aqua;
}

.label {
    padding-left: 6pt;
    padding-right: 6pt;
    border: solid;
    border-width: 1pt;
    border-color: greenyellow;
    flex-basis: 50pt;
}

.input-or-value {
    padding-left: 6pt;
    padding-right: 6pt;
    border: solid;
    border-width: 1pt;
    flex-grow: 3;
}

</style>
