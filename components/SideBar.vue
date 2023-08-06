<template>
    <span class="absolute text-white text-4xl top-5 left-4 cursor-pointer" onclick="openSidebar()">
        <i class="bi bi-filter-left px-2 bg-gray-900 rounded-md"></i>
    </span>

    <div class="sidebar fixed top-0 bottom-0 lg:left-0 p-2 w-[300px] overflow-y-auto text-center bg-gray-900">
        <SideBarLogo/>
        <SideBarLink link-name="Inicio"/>
        <SideBarSeparator/>
        <SideBarLinkDropdown/>
        <SideBarLink link-name="Proximamente"/>
    </div>
</template>

<script>


</script>