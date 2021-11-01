<template>
    <div>
        <nav class="bg-nav">
            <div class="max-w-7xl mx-auto px-2 sm:px-6 lg:px-8">
                <div class="relative flex items-center justify-between h-16">
                    <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
                        <!-- Mobile menu button-->
                        <button
                            v-on:click="isHidden = true"
                            type="button"
                            class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
                        >
                            <i class="fas fa-bars text-white text-3xl"></i>
                        </button>
                    </div>
                    <div
                        class="flex-1 flex items-center justify-center sm:items-stretch sm:justify-start"
                    >
                        <div class="flex-shrink-0 flex items-center">
                            <NuxtLink to="/">
                                <h1 class="text-white italic font-black text-3xl">rapiclub</h1>
                            </NuxtLink>
                        </div>
                        <div class="hidden sm:block sm:ml-6">
                            <div class="flex space-x-4">
                                <!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->
                                <NuxtLink
                                    to="/"
                                    v-for="navigation in navigations"
                                    :key="navigation"
                                    class="text-white block px-3 py-2 rounded-md text-sm font-light"
                                    aria-current="page"
                                >{{ navigation }}</NuxtLink>
                            </div>
                        </div>
                    </div>
                    <div
                        class="absolute inset-y-0 right-0 flex items-center pr-2 sm:static sm:inset-auto sm:ml-6 sm:pr-0"
                    >
                        <button
                            type="button"
                            class="bg-gray-800 p-1 rounded-full text-gray-400 hover:text-white focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white"
                        >
                            <!-- Heroicon name: outline/bell -->
                        </button>

                        <!-- Profile dropdown -->
                        <div class="ml-3 relative">
                            <div>
                                <button
                                    type="button"
                                    class="bg-gray-800 flex text-sm rounded-full focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white"
                                    id="user-menu-button"
                                    aria-expanded="false"
                                    aria-haspopup="true"
                                >
                                    <img
                                        class="h-8 w-8 rounded-full"
                                        src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
                                        alt
                                    />
                                </button>
                            </div>
                            <div
                                class="origin-top-right absolute right-0 mt-2 w-48 rounded-md shadow-lg py-1 bg-white ring-1 ring-black ring-opacity-5 focus:outline-none"
                                style="display: none"
                                role="menu"
                                aria-orientation="vertical"
                                aria-labelledby="user-menu-button"
                                tabindex="-1"
                            >
                                <a
                                    href="#"
                                    class="block px-4 py-2 text-sm text-gray-700"
                                    role="menuitem"
                                    tabindex="-1"
                                    id="user-menu-item-0"
                                >Your Profile</a>
                                <a
                                    href="#"
                                    class="block px-4 py-2 text-sm text-gray-700"
                                    role="menuitem"
                                    tabindex="-1"
                                    id="user-menu-item-1"
                                >Settings</a>
                                <a
                                    href="#"
                                    class="block px-4 py-2 text-sm text-gray-700"
                                    role="menuitem"
                                    tabindex="-1"
                                    id="user-menu-item-2"
                                >Sign out</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Mobile menu, show/hide based on menu state. -->
        </nav>
        <div class="sm:hidden bg-white" id="mobile-menu" v-if="isHidden">
            <div class="px-2 pt-2 pb-3 space-y-1">
                <button
                    v-on:click="isHidden = !isHidden"
                    type="button"
                    class="flex items-center justify-start pl-3 pt-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
                >
                    <span class="sr-only">Open main menu</span>

                    <i class="fas fa-times text-black text-3xl"></i>
                </button>
                <NuxtLink to="/">
                    <h1
                        class="text-red-500 italic text-left font-black text-3xl text-left ml-4 mt-4 mb-4"
                    >rapiclub</h1>
                </NuxtLink>
                <NuxtLink
                    to="/"
                    v-for="navigation in navigations"
                    :key="navigation"
                    class="text-white block px-3 py-2 rounded-md font-light text-left text-sm ml-2"
                    aria-current="page"
                >{{ navigation }}</NuxtLink>
            </div>
        </div>
    </div>
</template>

<script>
import './Navbar.css'
export default {
    name: 'Navbar',

    data() {
        return {
            navigations: [
                'Conocé Rapiclub',
                'Buscar Beneficios',
                'Términos y condiciones',
            ],
            isHidden: false,
        }
    }
}
</script>


