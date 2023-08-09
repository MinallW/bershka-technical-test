<template>
    <div class="text-gray-100 text-xl">
        <div class="flex items-center justify-center">
            <div class="flex-auto">
                <slot></slot>

            </div>
            <h1 class="font-bold text-gray-200 text-[15px]">{{ linkName }}</h1>
            <i class="bi bi-x cursor-pointer ml-28 lg:hidden" onclick="openSidebar()"></i>
        </div>
        <SideBarSeparator></SideBarSeparator>
    </div>
</template>

<script setup>
const props = defineProps({
    linkName: {
        type: String,
        required: true
    }
})
</script>