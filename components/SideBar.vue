<template>
    <span class="absolute text-white text-4xl top-5 left-4 cursor-pointer" onclick="openSidebar()">
        <i class="bi bi-filter-left px-2 bg-gray-900 rounded-md"></i>
    </span>

    <div class="sidebar fixed top-0 bottom-0 lg:left-0 p-2 w-[300px] overflow-y-auto text-center bg-gray-900">
        <SideBarLogo />
        <SideBarLink link-name="Inicio">
            <HomeIcon class="h-6 w-6" />
        </SideBarLink>
        <SideBarSeparator />
        <SideBarLinkDropdown />
        <SideBarLink link-name="Proximamente">
            <BeakerIcon class="h-6 w-6" />
        </SideBarLink>
    </div>
</template>

<script setup>
import { HomeIcon, BeakerIcon } from '@heroicons/vue/24/solid'
</script>