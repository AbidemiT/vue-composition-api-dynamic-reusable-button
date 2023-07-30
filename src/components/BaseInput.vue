<template>
    <template v-if="$attrs.type === 'text'">
        <label :for="label">{{ label }}</label>
        <!-- Manually bind input attributes with ($attrs) -->
        <input v-bind="$attrs" :placeholder="label" :id="label" class="field" :value="modelValue"
            @input="$emit('update:modelValue', $event.target.value)">
    </template>
    <template v-else-if="$attrs.type === 'radio'">
        <label :for="label">
            <input v-bind="$attrs" :placeholder="label" :id="label" class="field"
                @input="$emit('update:modelValue', $attrs.value)">
            {{ label }}
        </label>
    </template>
</template>

<script setup>
import { ref, onMounted, useAttrs } from 'vue';
console.log();
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