<script setup>
import AppHeader from "@/Components/Dashboard/AppHeader.vue";
import DataTable from "@/Components/Dashboard/DataTable.vue";
import ModalForm from "@/Components/ModalForm.vue";
import DashboardLayout from "@/Layouts/DashboardLayout.vue";

defineOptions({
    layout: DashboardLayout,
});
</script>

<template>
    <AppHeader title="Roles" />
    <ModalForm name="Create Role">
        <form>
        </form>
    </ModalForm>
    <DataTable />
</template>
