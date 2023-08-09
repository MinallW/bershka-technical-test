<template>
    <span class="sidebar fixed top-0 bottom-0 lg:left-0 p-3 w-[100px] overflow-y-auto text-center bg-gray-900" @click="toggleSidebar">
         <SideBarLogo class="hover:bg-blue-600 rounded-md cursor-pointer">
            <Bars4Icon class="h-6 w-6" />
        </SideBarLogo>
    </span>

    <div class="sidebar fixed top-0 bottom-0 lg:left-0 p-3 w-[300px] overflow-y-auto text-center bg-gray-900" v-if="isOpen">
        <!--  -->
        <SideBarLogo @click="toggleSidebar" class="hover:bg-blue-600 rounded-md cursor-pointer" link-name="BERSHKA">
            <Bars4Icon class="h-6 w-6" />
        </SideBarLogo>
        <!--  -->
        <SideBarLink link-name="Inicio">
            <HomeIcon class="h-6 w-6" />
        </SideBarLink>
        <!--  -->
        <SideBarSeparator />
        <!-- Women -->
        <SideBarLinkDropdown link-name="Mujer">
            <template v-slot:icon>
                <UserPlusIcon class="h-6 w-6" />
            </template>
            <template v-slot:sublinks>
                <SideBarDropdownSubLink link-name="Camisas"></SideBarDropdownSubLink>
                <SideBarDropdownSubLink link-name="Pantalones"></SideBarDropdownSubLink>
                <SideBarDropdownSubLink link-name="Cosplay idk"></SideBarDropdownSubLink>

            </template>
        </SideBarLinkDropdown>
        <!-- Women -->
        <!-- Men -->
        <SideBarLinkDropdown link-name="Hombre">
            <template v-slot:icon>
                <UserMinusIcon class="h-6 w-6" />
            </template>
            <template v-slot:sublinks>
                <SideBarDropdownSubLink link-name="Camisas"></SideBarDropdownSubLink>
                <SideBarDropdownSubLink link-name="Pantalones"></SideBarDropdownSubLink>

            </template>
        </SideBarLinkDropdown>
        <!-- Men -->
        <SideBarLink link-name="Proximamente">
            <BeakerIcon class="h-6 w-6" />
        </SideBarLink>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import {
    HomeIcon,
    BeakerIcon,
    UserMinusIcon,
    UserPlusIcon,
    Bars4Icon
} from '@heroicons/vue/24/outline'

const isOpen = ref(false);

function toggleSidebar() {
    isOpen.value = !isOpen.value;
}
</script>