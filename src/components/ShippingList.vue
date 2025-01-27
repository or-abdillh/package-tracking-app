<template>
    <section class="px-5 hover:bg-black-tersier duration-200 cursor-pointer">
        <div class="flex justify-between items-center py-4  border-b border-black-tersier">
            <!-- start -->
            <div class="flex items-center gap-5">
                <!-- icon -->
                <span class="grid place-items-center w-12 h-12 rounded-full"
                    :class="ship.status ? 'bg-green-300' : 'bg-orange-300'">
                    <i class="fa-solid fa-box text-white text-xl"></i>
                </span>
    
                <!-- detail -->
                <div>
                    <small class="uppercase text-gray-400">id number</small>
                    <p class="text-gray-200 text-lg">{{ ship.id }}</p>
                </div>
            </div>
    
            <!-- end -->
            <div>
                <p 
                    :class="ship.status ? 'text-green-400' : 'text-orange-400'">
                    {{ ship.status ? "Completed" : "On the way" }}
                </p>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">

interface Props {
    ship: {
        id: string,
        status: boolean
    }
}

const { ship } = defineProps<Props>()

</script>