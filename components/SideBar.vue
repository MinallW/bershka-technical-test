<template>
    <span class="sidebar fixed top-0 lg:left-0 p-3 w-[100px] h-[50px] text-center bg-gray-900 z-40"
        @click="toggleSidebar">
        <SideBarLogo class="hover:bg-blue-400 rounded-md cursor-pointer" link-name="">
            <Bars4Icon class="h-6 w-6" />
        </SideBarLogo>
    </span>
    <div class="sidebar fixed top-0 bottom-0 lg:left-0 p-3 w-80 overflow-y-auto text-center bg-gray-900 z-40" v-if="isOpen">
        <!--  -->
        <SideBarLogo @click="toggleSidebar" link-name="BERSHKA" class="cursor-pointer hover:bg-blue-400">
            <Bars4Icon class="h-6 w-6" />
        </SideBarLogo>
        <!--  -->
        <Search />
        <!--  -->
        <SideBarSeparator />
        <!--  -->
        <NuxtLink to="/">
            <SideBarLink link-name="Inicio">
                <HomeIcon class="h-6 w-6" />
            </SideBarLink>
        </NuxtLink>
        <!--  -->
        <SideBarSeparator />
        <!-- Women -->
        <SideBarLinkDropdown link-name="Mujer">
            <template v-slot:icon>
                <UserPlusIcon class="h-6 w-6" />
            </template>
            <template v-slot:sublinks>
                <NuxtLink to="/women/shirts">
                    <SideBarDropdownSubLink link-name="Camisas"></SideBarDropdownSubLink>
                </NuxtLink>
                <NuxtLink to="/women/pants">
                    <SideBarDropdownSubLink link-name="Pantalones"></SideBarDropdownSubLink>
                </NuxtLink>
            </template>
        </SideBarLinkDropdown>
        <!-- Women -->
        <!-- Men -->
        <SideBarLinkDropdown link-name="Hombre">
            <template v-slot:icon>
                <UserMinusIcon class="h-6 w-6" />
            </template>
            <template v-slot:sublinks>
                <NuxtLink to="/men/shirts">
                    <SideBarDropdownSubLink link-name="Camisas"></SideBarDropdownSubLink>
                </NuxtLink>
                <NuxtLink to="/men/pants">
                    <SideBarDropdownSubLink link-name="Pantalones"></SideBarDropdownSubLink>
                </NuxtLink>

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