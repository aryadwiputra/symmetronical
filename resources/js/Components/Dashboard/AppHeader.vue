<script setup>
import { Head } from "@inertiajs/vue3";

defineProps({
    title: {
        type: String,
        required: true,
    },
    subtitle: {
        type: String,
        required: false,
    },
});
</script>

<template>
    <Head :title="title" />
    <div class="flex items-center">
        <h1 class="text-lg font-semibold md:text-2xl">{{ title }}</h1>
    </div>
</template>
