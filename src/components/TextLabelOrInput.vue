<script setup lang="ts">
const props = withDefaults(defineProps<{
    name: string,
    isEdit: boolean
}>(),
    {
        isEdit: false
    })

</script>
<script lang="ts">
import { ref } from 'vue'
const text_value = ref("")


export default {
    data() {
        return {
            text_value
        }
    }
}
</script>

<template>
    <div class="flex-input">
        <div class="label">{{ name }}</div>
        <input v-model=text_value></input>
    </div>
</template>

<style scoped>
button {
    font-weight: bold;
}

.flex-input {
    display: flex;
}

.label {
    padding-right: 6pt;
}
</style>