<script setup lang="ts">
import { Button } from "@/Components/ui/button";

import { Link, Head } from "@inertiajs/vue3";
import DesktopSidebar from "@/Components/Dashboard/DesktopSidebar.vue";
import MobileSidebar from "@/Components/Dashboard/MobileSidebar.vue";
import AppHeader from "@/Components/Dashboard/AppHeader.vue";

defineProps({
    title: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <Head :title="title" />
    <div
        class="grid min-h-screen w-full md:grid-cols-[220px_1fr] lg:grid-cols-[280px_1fr]"
    >
        <!-- Desktop Sidebar -->
        <DesktopSidebar />
        <div class="flex flex-col">
            <!-- Mobile Sidebar -->
            <MobileSidebar />
            <main class="flex flex-1 flex-col gap-4 p-4 lg:gap-6 lg:p-6">
                <AppHeader :title="title" />
                <slot />
            </main>
        </div>
    </div>
</template>
