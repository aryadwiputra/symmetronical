<script setup lang="ts">
import { Button } from "@/Components/ui/button";
import {
    Card,
    CardContent,
    CardDescription,
    CardFooter,
    CardHeader,
    CardTitle,
} from "@/Components/ui/card";
import { Input } from "@/Components/ui/input";
import { Label } from "@/Components/ui/label";
import { Head, Link, useForm } from "@inertiajs/vue3";


defineProps({
    canResetPassword: {
        type: Boolean,
    },
    status: {
        type: String,
    },
});

const form = useForm({
    email: "",
    password: "",
    remember: false,
});

const submit = () => {
    form.post(route("login"), {
        onFinish: () => form.reset("password"),
    });
};
</script>

<template>
    <Head title="Login" />
    <div class="h-screen flex justify-center items-center">
        <Card class="w-full max-w-sm">
            <CardHeader>
                <CardTitle class="text-2xl"> Login </CardTitle>
                <CardDescription>
                    Enter your email below to login to your account.
                </CardDescription>
            </CardHeader>
            <form @submit.prevent="submit">
                <CardContent class="grid gap-4">
                    <div class="grid gap-2">
                        <Label for="email">Email</Label>
                        <Input
                            id="email"
                            type="email"
                            placeholder="user@example.com"
                            v-model="form.email"
                            required
                        />
                    </div>
                    <div class="grid gap-2">
                        <Label for="password">Password</Label>
                        <Input
                            id="password"
                            type="password"
                            v-model="form.password"
                            required
                            placeholder="********"
                        />
                        <Link
                            href="/forgot-password"
                            class="underline text-sm text-blue-400 hover:text-blue-600"
                            >Forgot password?</Link
                        >
                    </div>
                </CardContent>
                <CardFooter>
                    <Button class="w-full" type="submit" :disabled="form.processing" > Sign in </Button>
                </CardFooter>
            </form>
        </Card>
    </div>
</template>
