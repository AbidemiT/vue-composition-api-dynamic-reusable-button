<template>
    <label>{{ label }}</label>
    <select @change="$emit('update:modelValue', $event.target.value)">
        <option v-for="(option, i) in options" :key="option + '-' + i" :value="option" :selected="option === modelValue">{{ option }}</option>
    </select>
</template>

<script setup>
defineEmits(['update:modelValue']);
defineProps({
    label: {
        type: String,
        default: ''
    },
    modelValue: {
        type: [String, Number],
        default: ''
    },
    options: {
        type: Array,
        default: ["Select Option"]
    }
});
</script>