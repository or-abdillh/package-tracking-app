<template>
    <main class="fixed bottom-0 left-0 right-0">
        <!-- inner wrapper -->
        <section class="w-full md:w-5/12 lg:w-4/12 xl:w-3/12 md:mx-auto px-8 pb-8 pt-6 flex items-start justify-around gap-3 border-t-2 border-black-secondary">
            <template v-for="link in links" :key="link">
                <!-- link -->
                <button @click="active = link.title" class="cursor-pointer">
                    <i class="fa-solid text-2xl duration-200" 
                        :class="[
                            link.icon,
                            active === link.title ? 'text-gray-100' : 'text-gray-700'
                        ]"></i>
                </button>
            </template>
        </section>
    </main>
</template>

<script setup lang="ts">

import { ref } from 'vue';

// initial
const links: { title: string, icon: string }[] = [
    { title: "Home", icon: "fa-home" },
    { title: "Tracking", icon: "fa-location-dot" },
    { title: "Search", icon: "fa-search" },
    { title: "Profile", icon: "fa-circle-user" }
]

// refs
const active = ref<string>(links[0].title)

</script>