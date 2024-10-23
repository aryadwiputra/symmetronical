<template>
    <div class="min-h-screen bg-gray-50">
        <!-- Navigation -->
        <nav class="bg-white shadow">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="flex justify-between h-16">
                    <div class="flex">
                        <div class="flex-shrink-0 flex items-center">
                            <RocketIcon class="h-8 w-8 text-indigo-600" />
                            <span class="ml-2 text-xl font-bold text-gray-900"
                                >Symmetronical</span
                            >
                        </div>
                    </div>
                    <div class="flex items-center">
                        <a
                            href="#"
                            class="text-gray-500 hover:text-gray-700 px-3 py-2 rounded-md text-sm font-medium"
                            >Features</a
                        >
                        <a
                            href="#"
                            class="text-gray-500 hover:text-gray-700 px-3 py-2 rounded-md text-sm font-medium"
                            >Pricing</a
                        >
                        <a
                            href="#"
                            class="text-gray-500 hover:text-gray-700 px-3 py-2 rounded-md text-sm font-medium"
                            >Contact</a
                        >
                        <button
                            class="ml-4 px-4 py-2 border border-transparent text-sm font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
                        >
                            Sign Up
                        </button>
                    </div>
                </div>
            </div>
        </nav>

        <!-- Hero Section -->
        <div class="relative bg-white overflow-hidden">
            <div class="max-w-7xl mx-auto">
                <div
                    class="relative z-10 pb-8 bg-white sm:pb-16 md:pb-20 lg:max-w-2xl lg:w-full lg:pb-28 xl:pb-32"
                >
                    <main
                        class="mt-10 mx-auto max-w-7xl px-4 sm:mt-12 sm:px-6 md:mt-16 lg:mt-20 lg:px-8 xl:mt-28"
                    >
                        <div class="sm:text-center lg:text-left">
                            <h1
                                class="text-4xl tracking-tight font-extrabold text-gray-900 sm:text-5xl md:text-6xl"
                            >
                                <span class="block xl:inline"
                                    >Supercharge your</span
                                >
                                <span class="block text-indigo-600 xl:inline"
                                    > business growth</span
                                >
                            </h1>
                            <p
                                class="mt-3 text-base text-gray-500 sm:mt-5 sm:text-lg sm:max-w-xl sm:mx-auto md:mt-5 md:text-xl lg:mx-0"
                            >
                                Empower your team with our cutting-edge SaaS
                                solution. Streamline workflows, boost
                                productivity, and drive innovation.
                            </p>
                            <div
                                class="mt-5 sm:mt-8 sm:flex sm:justify-center lg:justify-start"
                            >
                                <div class="rounded-md shadow">
                                    <a
                                        href="#"
                                        class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 md:py-4 md:text-lg md:px-10"
                                    >
                                        Get started
                                    </a>
                                </div>
                                <div class="mt-3 sm:mt-0 sm:ml-3">
                                    <a
                                        href="#"
                                        class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-indigo-700 bg-indigo-100 hover:bg-indigo-200 md:py-4 md:text-lg md:px-10"
                                    >
                                        Live demo
                                    </a>
                                </div>
                            </div>
                        </div>
                    </main>
                </div>
            </div>
            <div class="lg:absolute lg:inset-y-0 lg:right-0 lg:w-1/2">
                <img
                    class="h-56 w-full object-cover sm:h-72 md:h-96 lg:w-full lg:h-full"
                    src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80"
                    alt="Dashboard preview"
                />
            </div>
        </div>

        <!-- Features Section -->
        <div class="py-12 bg-white">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="lg:text-center">
                    <h2
                        class="text-base text-indigo-600 font-semibold tracking-wide uppercase"
                    >
                        Features
                    </h2>
                    <p
                        class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-gray-900 sm:text-4xl"
                    >
                        Everything you need to succeed
                    </p>
                    <p class="mt-4 max-w-2xl text-xl text-gray-500 lg:mx-auto">
                        Our platform provides all the tools you need to take
                        your business to the next level.
                    </p>
                </div>

                <div class="mt-10">
                    <dl
                        class="space-y-10 md:space-y-0 md:grid md:grid-cols-2 md:gap-x-8 md:gap-y-10"
                    >
                        <div
                            v-for="feature in features"
                            :key="feature.name"
                            class="relative"
                        >
                            <dt>
                                <div
                                    class="absolute flex items-center justify-center h-12 w-12 rounded-md bg-indigo-500 text-white"
                                >
                                    <component
                                        :is="feature.icon"
                                        class="h-6 w-6"
                                    />
                                </div>
                                <p
                                    class="ml-16 text-lg leading-6 font-medium text-gray-900"
                                >
                                    {{ feature.name }}
                                </p>
                            </dt>
                            <dd class="mt-2 ml-16 text-base text-gray-500">
                                {{ feature.description }}
                            </dd>
                        </div>
                    </dl>
                </div>
            </div>
        </div>

        <!-- Pricing Section -->
        <div class="bg-gray-100 py-12">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="sm:flex sm:flex-col sm:align-center">
                    <h2
                        class="text-3xl font-extrabold text-gray-900 sm:text-center"
                    >
                        Pricing Plans
                    </h2>
                    <p class="mt-5 text-xl text-gray-500 sm:text-center">
                        Start building for free, then add a site plan to go
                        live. Account plans unlock additional features.
                    </p>
                </div>
                <div
                    class="mt-12 space-y-4 sm:mt-16 sm:space-y-0 sm:grid sm:grid-cols-2 sm:gap-6 lg:max-w-4xl lg:mx-auto xl:max-w-none xl:mx-0 xl:grid-cols-3"
                >
                    <div
                        v-for="plan in plans"
                        :key="plan.name"
                        class="border border-gray-200 rounded-lg shadow-sm divide-y divide-gray-200"
                    >
                        <div class="p-6">
                            <h3
                                class="text-lg leading-6 font-medium text-gray-900"
                            >
                                {{ plan.name }}
                            </h3>
                            <p class="mt-4 text-sm text-gray-500">
                                {{ plan.description }}
                            </p>
                            <p class="mt-8">
                                <span
                                    class="text-4xl font-extrabold text-gray-900"
                                    >${{ plan.price }}</span
                                >
                                <span
                                    class="text-base font-medium text-gray-500"
                                    >/mo</span
                                >
                            </p>
                            <a
                                href="#"
                                class="mt-8 block w-full bg-indigo-600 border border-transparent rounded-md py-2 text-sm font-semibold text-white text-center hover:bg-indigo-700"
                            >
                                {{ plan.cta }}
                            </a>
                        </div>
                        <div class="pt-6 pb-8 px-6">
                            <h4
                                class="text-sm font-medium text-gray-900 tracking-wide uppercase"
                            >
                                What's included
                            </h4>
                            <ul class="mt-6 space-y-4">
                                <li
                                    v-for="feature in plan.features"
                                    :key="feature"
                                    class="flex space-x-3"
                                >
                                    <CheckIcon
                                        class="flex-shrink-0 h-5 w-5 text-green-500"
                                    />
                                    <span class="text-sm text-gray-500">{{
                                        feature
                                    }}</span>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- CTA Section -->
        <div class="bg-indigo-700">
            <div
                class="max-w-2xl mx-auto text-center py-16 px-4 sm:py-20 sm:px-6 lg:px-8"
            >
                <h2 class="text-3xl font-extrabold text-white sm:text-4xl">
                    <span class="block">Boost your productivity.</span>
                    <span class="block">Start using our app today.</span>
                </h2>
                <p class="mt-4 text-lg leading-6 text-indigo-200">
                    Unlock the full potential of your business with our powerful
                    SaaS platform. Join thousands of satisfied customers and
                    transform the way you work.
                </p>
                <a
                    href="#"
                    class="mt-8 w-full inline-flex items-center justify-center px-5 py-3 border border-transparent text-base font-medium rounded-md text-indigo-600 bg-white hover:bg-indigo-50 sm:w-auto"
                >
                    Sign up for free
                </a>
            </div>
        </div>

        <!-- Footer -->
        <footer class="bg-white">
            <div
                class="max-w-7xl mx-auto py-12 px-4 sm:px-6 md:flex md:items-center md:justify-between lg:px-8"
            >
                <div class="flex justify-center space-x-6 md:order-2">
                    <a href="#" class="text-gray-400 hover:text-gray-500">
                        <span class="sr-only">Twitter</span>
                        <TwitterIcon class="h-6 w-6" />
                    </a>
                    <a href="#" class="text-gray-400 hover:text-gray-500">
                        <span class="sr-only">GitHub</span>
                        <GithubIcon class="h-6 w-6" />
                    </a>
                    <a href="#" class="text-gray-400 hover:text-gray-500">
                        <span class="sr-only">LinkedIn</span>
                        <LinkedinIcon class="h-6 w-6" />
                    </a>
                </div>
                <div class="mt-8 md:mt-0 md:order-1">
                    <p class="text-center text-base text-gray-400">
                        &copy; 2023 Symmetronical, Inc. All rights reserved.
                    </p>
                </div>
            </div>
        </footer>
    </div>
</template>

<script setup>
import {
    RocketIcon,
    LayoutIcon,
    UsersIcon,
    BarChartIcon,
    LockIcon,
    CheckIcon,
    TwitterIcon,
    GithubIcon,
    LinkedinIcon,
} from "lucide-vue-next";

const features = [
    {
        name: "Intuitive Dashboard",
        description:
            "Get a quick overview of your business performance with our easy-to-use dashboard.",
        icon: LayoutIcon,
    },
    {
        name: "Team Collaboration",
        description:
            "Work seamlessly with your team members in real-time, boosting productivity.",
        icon: UsersIcon,
    },
    {
        name: "Advanced Analytics",
        description:
            "Gain valuable insights with our powerful analytics and reporting tools.",
        icon: BarChartIcon,
    },
    {
        name: "Enterprise-grade Security",
        description:
            "Rest easy knowing your data is protected by state-of-the-art security measures.",
        icon: LockIcon,
    },
];

const plans = [
    {
        name: "Hobby",
        price: 0,
        description: "All the basics for starting a new business",
        cta: "Sign up for free",
        features: ["Up to 5 users", "Basic analytics", "Email support"],
    },
    {
        name: "Pro",
        price: 79,
        description: "Everything you need for a growing business",
        cta: "Start free trial",
        features: [
            "Up to 50 users",
            "Advanced analytics",
            "Priority support",
            "Custom integrations",
        ],
    },
    {
        name: "Enterprise",
        price: 299,
        description: "Advanced features for scaling your business",
        cta: "Contact sales",
        features: [
            "Unlimited users",
            "Advanced analytics",
            "24/7 phone support",
            "Custom integrations",
            "Dedicated account manager",
        ],
    },
];
</script>
