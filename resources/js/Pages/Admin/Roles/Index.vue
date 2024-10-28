<script setup>
import AppHeader from "@/Components/Dashboard/AppHeader.vue";
import DataTable from "@/Components/Dashboard/DataTable.vue";
import { Button } from "@/Components/ui/button";
import DashboardLayout from "@/Layouts/DashboardLayout.vue";
import { Link } from "@inertiajs/vue3";
import { FileDown, FileUp, Plus } from "lucide-vue-next";

import { computed } from "vue";

defineOptions({
    layout: DashboardLayout,
});

const props = defineProps({
    roles: { type: Array, required: true }, // ubah type ke Array
});

// Header tabel yang statis
const headers = ["Roles", "Name", "Permissions"];

// Map data dari roles untuk menjadi rows
const rows = computed(() => {
    return props.roles.map((role) => ({
        roles: role.name, // Nama role
        name: role.name, // Nama yang ditampilkan
        permissions: role.permissions.map((p) => p.name).join(", "), // Gabungkan permissions
    }));
});

// Fungsi handler
const handleEdit = (row) => {
    console.log("Edit row:", row);
};

const handleDelete = (row) => {
    console.log("Delete row:", row);
};
</script>

<template>
    <AppHeader title="Roles" subtitle="List of all roles data." />
    <div class="inline-flex gap-2">
        <Button :as="Link" :href="route('admin.roles.create')" class="mb-4">
            <Plus class="mr-2 h-4 w-4" />
            Create
        </Button>
        <Button disabled as="Link" href="#" class="mb-4">
            <FileDown class="mr-2 h-4 w-4" />
            Import
        </Button>
        <Button disabled as="Link" href="#" class="mb-4">
            <FileUp class="mr-2 h-4 w-4" />
            Export
        </Button>
    </div>
    <DataTable
        caption="A list of all roles data."
        :headers="headers"
        :rows="rows"
        @edit="handleEdit"
        @delete="handleDelete"
    />
</template>
