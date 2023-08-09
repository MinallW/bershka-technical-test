<template>
    <div class="p-2.5 mt-3 flex items-center rounded-md px-4 duration-300 cursor-pointer hover:bg-blue-400 text-white"
        @click="toggleDropdown">
        <slot name="icon"></slot>
        <div class="flex justify-between w-full items-center">
            <span class="text-[15px] ml-4 text-gray-200 font-bold">{{ linkName }}</span>
            <ArrowSmallUpIcon class="h-6 w-6" v-if="isOpen"/>
            <ArrowSmallDownIcon class="h-6 w-6" v-else/>
        </div>
    </div>
    <div v-if="isOpen" class="text-left text-sm mt-2 w-4/5 mx-auto text-gray-200 font-bold">
        <slot name="sublinks"></slot>
    </div>
</template>

<script setup>
import {
    ArrowSmallUpIcon,
    ArrowSmallDownIcon
} from '@heroicons/vue/24/outline'
import { ref } from 'vue';

const props = defineProps({
    linkName: {
        type: String,
        required: true
    }
})
const isOpen = ref(false);

function toggleDropdown() {
    isOpen.value = !isOpen.value;
}
</script>