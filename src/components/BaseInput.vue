<template>
    <label>{{ label }}</label>
    <!-- Manually bind input attributes with ($attrs) -->
    <input v-bind="$attrs" :placeholder="label" class="field" :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)">
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
    }
});
</script>