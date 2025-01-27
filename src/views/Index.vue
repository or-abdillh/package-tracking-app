<template>
    <BaseLayout>
        <!-- profile section -->
        <section class="grid grid-cols-10 gap-6 mb-4">
            <!-- user avatar -->
            <div class="col-span-6 bg-black-secondary p-2 flex items-start gap-4 rounded-3xl">
                <!-- picture -->
                <img class="w-12 h-12 rounded-2xl" src="/images/user.png" alt="Sitting And Smiling – Download this photo by Brooke Cagle on Unsplash">

                <!-- information -->
                <div>
                    <p class="text-white text-lg font-medium">Stive Kote</p>
                    <p class="text-gray-500 text-sm">17 Jan, 2024</p>
                </div>
            </div>

            <!-- coin counter -->
            <div class="col-span-4 col-start-8 bg-black-secondary px-3 h-full py-2 rounded-3xl grid place-items-center">
                <p class="text-white font-medium">
                    <span class=" text-green-600 text-lg">872</span> Coins
                </p>
            </div>
        </section>

        <!-- search section -->
        <section class="w-full grid grid-cols-6 bg-black-secondary p-2 rounded-3xl mb-4">
            <div class="col-span-5 flex items-center gap-4 text-gray-200 ps-4">
                <!-- icon -->
                <i class="fa-solid fa-search col-span-1"></i>
    
                <!-- field -->
                <input class="col-span-3 placeholder:text-gray-400 text-gray-200 text-lg focus:outline-0" type="search" placeholder="Track Your Package">
            </div>

            <!-- scanner -->
            <button class="col-span-1 grid place-items-center bg-black-tersier h-12 rounded-2xl">
                <i class="fa-solid fa-qrcode text-gray-200 text-xl"></i>
            </button>

        </section>

        <!-- banner section -->
        <section class="w-full px-6 py-5 rounded-3xl bg-green-400 grid grid-cols-2 overflow-hidden mb-4">
            <!-- copywriting -->
            <div class="col-span-1 text-white">
                <p>Discount</p>
                <p class="mb-4 mt-1 text-3xl font-semibold">20% OFF</p>

                <!-- CTA -->
                <button class="bg-black px-6 py-3 rounded-full uppercase text-sm text-white">get discount</button>
            </div>

            <!-- illustration -->
            <div class="col-span-1 relative">
                <!-- big -->
                <img class="w-26 absolute bottom-0 left-0" src="/images/card-board-big.png" alt="card-board">

                <!-- small -->
                <img class="w-24 absolute -right-12 bottom-3 md:right-0" src="/images/card-board-small.png" alt="card-board">
            </div>
        </section>

        <!-- menu section -->
        <section class="w-full flex gap-2 justify-between mb-6">
            <template v-for="menu in menus" :key="menu">
                <!-- menu -->
                <button class="bg-black-secondary text-gray-200 rounded-2xl p-4 flex flex-col items-center gap-3 w-full cursor-pointer hover:bg-black-tersier duration-200">
                    <!-- icon -->
                    <i class="fa-solid text-lg" :class="menu.icon"></i>
                    <!-- title -->
                    <p>{{ menu.title }}</p>
                </button>
            </template>
        </section>

        <!-- recent shipping -->
        <section class="w-full">
            <!-- header -->
            <div class="flex justify-between items-center mb-4">
                <p class="text-white text-xl font-medium">Recent Shipping</p>

                <!-- action -->
                <button class=" inline-flex gap-3 items-center text-lg text-green-600">
                    See all 
                    <i class="fa-solid fa-chevron-right text-sm"></i>
                </button>
            </div>

            <!-- wrapper -->
            <div class="flex flex-col overflow-hidden rounded-3xl bg-black-secondary">
                <template v-for="ship in shippings" :key="ship">
                    <!-- shipping list -->
                    <ShippingList :ship="ship" />
                </template>
            </div>
        </section>
    </BaseLayout>
</template>

<script setup lang="ts">

import BaseLayout from '@/layouts/Base.vue';
import ShippingList from '@/components/ShippingList.vue';

// initials
const menus: { title: string, icon: string }[] = [
    { title: "Price", icon: "fa-money-bill" },
    { title: "Point", icon: "fa-location-dot" },
    { title: "News", icon: "fa-newspaper" },
    { title: "Info", icon: "fa-circle-info" }
]

const shippings: { id: string, status: boolean }[] = [
    { id: "A425HYJ8", status: false },
    { id: "A153KOJ2", status: true },
    { id: "B672PLM9", status: true },
    { id: "C983QWE4", status: false },
    { id: "D234RTY7", status: true },
    { id: "E567UIO1", status: false },
    { id: "F890ASD3", status: true }
]
</script>