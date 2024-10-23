<script setup lang="ts">
import { Button } from "@/Components/ui/button";
import { Input } from "@/Components/ui/input";
import { Label } from "@/Components/ui/label";

import { Link } from "@inertiajs/vue3";
</script>

<template>
    <div
        class="w-full lg:grid lg:min-h-[600px] lg:grid-cols-2 xl:min-h-[800px]"
    >
        <div class="flex items-center justify-center py-12">
            <div class="mx-auto grid w-[350px] gap-6">
                <div class="grid gap-2 text-center">
                    <h1 class="text-3xl font-bold">Login</h1>
                    <p class="text-balance text-muted-foreground">
                        Enter your email below to login to your account
                    </p>
                </div>
                <div class="grid gap-4">
                    <div class="grid gap-2">
                        <Label for="email">Email</Label>
                        <Input
                            id="email"
                            type="email"
                            placeholder="m@example.com"
                            required
                        />
                    </div>
                    <div class="grid gap-2">
                        <div class="flex items-center">
                            <Label for="password">Password</Label>
                            <a
                                href="/forgot-password"
                                class="ml-auto inline-block text-sm underline"
                            >
                                Forgot your password?
                            </a>
                        </div>
                        <Input id="password" type="password" required />
                    </div>
                    <Button type="submit" class="w-full"> Login </Button>
                    <Button variant="outline" class="w-full">
                        Login with Google
                    </Button>
                </div>
                <div class="mt-4 text-center text-sm">
                    Don't have an account?
                    <Link :href="route('register')" class="underline">
                        Sign up
                    </Link>
                </div>
            </div>
        </div>
        <div class="hidden bg-muted lg:block">
            <img
                src="https://images.unsplash.com/photo-1616763355603-9755a640a287?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1374&q=80"
                alt="Image"
                width="1920"
                height="1080"
                class="h-full w-full object-cover dark:brightness-[0.2] dark:grayscale"
            />
        </div>
    </div>
</template>
