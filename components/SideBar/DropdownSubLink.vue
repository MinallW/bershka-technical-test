<template>
    <slot></slot>
    <h1 class="cursor-pointer p-2 hover:bg-blue-600 rounded-md mt-1">
        {{ linkName }}
    </h1>
</template>

<script setup>
const props = defineProps({
    linkName: {
        type: String,
        required: true
    }
})

</script>