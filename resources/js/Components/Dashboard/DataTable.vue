<script setup lang="ts">
import { defineProps, defineEmits, toRefs } from "vue";
import {
    Table,
    TableBody,
    TableCaption,
    TableCell,
    TableHead,
    TableHeader,
    TableRow,
} from "@/Components/ui/table";
import { Button } from "@/Components/ui/button";

const props = defineProps({
    caption: { type: String, default: "" }, // Teks keterangan untuk tabel
    headers: { type: Array, required: true }, // Header tabel (array string)
    rows: { type: Array, required: true }, // Data baris (array object)
    actions: { type: Boolean, default: true }, // Apakah ada aksi edit & delete
});

const emit = defineEmits(["edit", "delete"]); // Emit untuk aksi
</script>

<template>
    <Table>
        <TableCaption v-if="caption">{{ caption }}</TableCaption>
        <TableHeader>
            <TableRow>
                <TableHead
                    v-for="header in headers"
                    :key="header"
                    class="text-left"
                >
                    {{ header }}
                </TableHead>
                <!-- Kolom tambahan untuk Actions -->
                <TableHead v-if="actions" class="text-right">Actions</TableHead>
            </TableRow>
        </TableHeader>
        <TableBody>
            <TableRow v-for="(row, rowIndex) in rows" :key="rowIndex">
                <!-- Render setiap sel data sesuai urutan headers -->
                <TableCell
                    v-for="header in headers"
                    :key="header"
                    class="font-medium"
                >
                    {{ row[header.toLowerCase()] }}
                </TableCell>

                <!-- Actions Edit dan Delete -->
                <TableCell v-if="actions" class="text-right space-x-2">
                    <Button
                        variant="outline"
                        @click="$emit('edit', row)"
                        size="sm"
                    >
                        Edit
                    </Button>
                    <Button
                        variant="outline"
                        @click="$emit('delete', row)"
                        size="sm"
                        class="text-red-600"
                    >
                        Delete
                    </Button>
                </TableCell>
            </TableRow>
        </TableBody>
    </Table>
</template>
