<template>
    <main class="w-full bg-black min-h-screen">
        <!-- fixed wrapper -->
        <main class="md:w-5/12 lg:w-4/12 xl:w-3/12 md:mx-auto">
            <slot />
        </main>

        <!-- bottom bar -->
        <BottomBar />
    </main>
</template>

<script setup lang="ts">

import BottomBar from "@/components/BottomBar.vue"

</script>