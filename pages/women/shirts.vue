<template>
    <ProductList title="Camisas Mujer" :products="products" />
</template>

<script setup>
const products = [
    {
        id: 1,
        name: 'Camisa básica',
        href: '#',
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-01.jpg',
        imageAlt: "Front of men's Basic Tee in Negro.",
        price: '$35',
        color: 'Negro',
    },
    {
        id: 2,
        name: 'Camisa básica 2',
        href: '#',
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-04.jpg',
        imageAlt: "Front of men's Basic Tee in Negro.",
        price: '$35',
        color: 'Negro',
    },
    {
        id: 3,
        name: 'Camisa básica 3',
        href: '#',
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-03.jpg',
        imageAlt: "Front of men's Basic Tee in Negro.",
        price: '$35',
        color: 'Negro',
    },
    {
        id: 5,
        name: 'Camisa básica 5',
        href: '#',
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-02.jpg',
        imageAlt: "Front of men's Basic Tee in Negro.",
        price: '$35',
        color: 'Negro',
    },
    {
        id: 6,
        name: 'Camisa básica 6',
        href: '#',
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-01.jpg',
        imageAlt: "Front of men's Basic Tee in Negro.",
        price: '$35',
        color: 'Negro',
    },
    {
        id: 7,
        name: 'Camisa básica 2',
        href: '#',
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-04.jpg',
        imageAlt: "Front of men's Basic Tee in Negro.",
        price: '$35',
        color: 'Negro',
    },
    {
        id: 8,
        name: 'Camisa básica 3',
        href: '#',
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-03.jpg',
        imageAlt: "Front of men's Basic Tee in Negro.",
        price: '$35',
        color: 'Negro',
    },
    {
        id: 9,
        name: 'Camisa básica 5',
        href: '#',
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-02.jpg',
        imageAlt: "Front of men's Basic Tee in Negro.",
        price: '$35',
        color: 'Negro',
    }
    // More products...
]
</script>