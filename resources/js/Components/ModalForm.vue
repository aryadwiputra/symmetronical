<script setup lang="ts">
import {
    Dialog,
    DialogContent,
    DialogDescription,
    DialogFooter,
    DialogHeader,
    DialogTitle,
    DialogTrigger,
} from "@/Components/ui/dialog";
import { Button } from "./ui/button";

defineProps({
    name: {
        type: String,
    },
});
</script>

<template>
    <Dialog>
        <DialogTrigger class="inline-flex w-1">
            <Button> {{ name }} </Button>
        </DialogTrigger>
        <DialogContent>
            <DialogHeader>
                <DialogTitle>{{ name }}</DialogTitle>
                <DialogDescription>
                    <slot />
                </DialogDescription>
            </DialogHeader>

            <DialogFooter>
                <Button type="submit"> Save changes </Button>
            </DialogFooter>
        </DialogContent>
    </Dialog>
</template>
