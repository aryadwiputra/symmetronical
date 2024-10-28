<script setup>
import AppHeader from "@/Components/Dashboard/AppHeader.vue";
import { Button } from "@/Components/ui/button";
import { Input } from "@/Components/ui/input";
import { Label } from "@/Components/ui/label";
import DashboardLayout from "@/Layouts/DashboardLayout.vue";
import { Link, useForm } from "@inertiajs/vue3";
import { ArrowLeft } from "lucide-vue-next";

defineOptions({
    layout: DashboardLayout,
});

const form = useForm({
    name: "",
});
</script>

<template>
    <!-- Back Button -->
    <div class="inline-flex">
        <Button size="sm" :as="Link" :href="route('admin.roles.index')">
            <ArrowLeft class="mr-2 h-4 w-4" />Back</Button
        >
    </div>
    <AppHeader title="Create Role" />
    <!-- Form to create a new role -->
    <div class="mt-4">
        <form @submit.prevent="submit">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                <div>
                    <Label for="name">Role Name</Label>
                    <Input
                        id="name"
                        type="text"
                        v-model="form.name"
                        required
                        autofocus
                        placeholder="Enter role name"
                        class="mt-1 block w-full"
                    />
                    <InputError class="mt-2" :message="form.errors.name" />
                </div>

                <div></div>
            </div>
        </form>
    </div>
</template>
