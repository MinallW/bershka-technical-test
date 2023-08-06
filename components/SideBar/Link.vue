<template>
    <div class="p-2.5 mt-3 flex items-center rounded-md px-4 duration-300 cursor-pointer hover:bg-blue-600 text-white">
        <slot></slot>
        <span class="text-[15px] ml-4 text-gray-200 font-bold">{{ linkName }}</span>
    </div>
</template>

<script setup>
const props = defineProps({
    linkName: String
})
</script>