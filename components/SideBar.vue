<template>
    <span class="sidebar fixed top-0 lg:left-0 p-3 min-w-[200px] w-[100px] h-[50px] text-center bg-gray-900 z-40"
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
        <SideBarLink link-name="Función Categorías" @click="callCategoryFunction">
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


// Teniendo en cuenta que las rutas de pantalones y camisas están separadas por categorías (rutas) de hombre y mujer (men and women)
// Aquí implementaré la función getCategoryPath, con el mismo objeto dado.
const categories = [
    {
        name: 'category1',
        subcategories: [
            {
                name: 'category2',
                subcategories: []
            },
            {
                name: 'category3',
                subcategories: [
                    {
                        name: 'category4',
                        subcategories: []
                    }
                ]
            }
        ]
    },
    {
        name: 'category5',
        subcategories: []
    }
];

// TO-DO: Implement this function, usando ternarios because why not? <- se pueden usar ifs también, Simple is better but, testing .reduce
// Esta función puede ser usada en el input search, aunque actualmente está con un objeto más sencillo de rutas.

const getCategoryPath = (categories, categoryName, currentPath = '/') =>
    categories.reduce(
        (path, category) =>
            path ||
            (category.name === categoryName
                ? currentPath + category.name
                : category.subcategories.length > 0
                    ? getCategoryPath(category.subcategories, categoryName, currentPath + category.name + '/')
                    : null),
        null
    );

// OUTPUT SAMPLES <- Works on Console!!
function callCategoryFunction() {
    console.log(getCategoryPath(categories, 'category4')); // should output: '/category1/category3/category4'
    console.log(getCategoryPath(categories, 'category2')); // should output: '/category1/category2'
    console.log(getCategoryPath(categories, 'category5')); // should output: '/category5'
}

</script>