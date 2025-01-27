<template>
    <main class="w-full bg-black min-h-screen pb-24">
        <!-- fixed wrapper -->
        <main class="md:w-5/12 lg:w-4/12 xl:w-3/12 md:mx-auto">
            <section class="p-4">
                <slot />
            </section>
        </main>

        <!-- bottom bar -->
        <BottomBar />
    </main>
</template>

<script setup lang="ts">

import BottomBar from "@/components/BottomBar.vue"

</script>