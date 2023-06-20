<script setup>
import { ref } from 'vue';
import { Link } from '@inertiajs/vue3';
import MenuIcon from 'vue-material-design-icons/Menu.vue';
import MagnifyIcon from 'vue-material-design-icons/Magnify.vue';
import SideNavItem from '@/Components/SideNavItem.vue';

// NOTE TO SELF
// Run npm run dev
// Run php artisan serve

let openSideNav = ref(true);
</script>

<template>
    <div class="relative">
        <div id="TopNav" class="w-[100%] h-[60px] fixed bg-black z-20 flex items-center justify-between">
            <div class="flex items-center">
                <button @click="openSideNav = !openSideNav" class="inline-block p-2 ml-3 rounded-full cursor-pointer hover:bg-gray-800">
                    <MenuIcon fillColor="#FFFFFF" :size="26" />
                </button>
                <div class="mx-2"></div>
                <div class="flex items-center justify-center mr-10 text-white cursor-pointer">
                    YOUTUBE
                </div>
            </div>

            <div class="w-[600px] md:block hidden">
                <div class="rounded-full flex items-center bg-[#222222]">
                    <input
                        type="text"
                        class="
                            form-control
                            block
                            w-full
                            px-5
                            py-1.5
                            text-base
                            font-normal
                            text-gray-200
                            bg-black
                            placeholder-gray-400
                            bg-clip-padding
                            border
                            border-solid
                            border-l-gray-700
                            border-r-gray-700
                            rounded-l-full
                            ease-in-out
                            m-0
                            border-transparent
                            focus-ring-0
                        "
                        placeholder="Search"
                    />
                    <MagnifyIcon class="mx-6" fillColor="#FFFFFF" :size="23" />
                </div>
            </div>

            <div>
                <img
                    class="mx-8 rounded-full"
                    width="35"
                    src="https://yt3.ggpht.com/yti/AHyvSCAFJ6g9MbHJKTba65j-9N4ZPPkODN5_VnFGkez5=s88-c-k-c0x00ffffff-no-rj-mo"
                />
            </div>
        </div>
        <div
            id="SideNav"
            class="h-[100%] fixed z-0 bg-black"
            :class="[!openSideNav ? 'w-[70px]' : 'w-[240px]']"
        >
            <ul 
                class="mt-[60px] w-full"
                :class="[!openSideNav ? 'p-2' : 'px-5 pb-2 pt-[7px]']">
                <SideNavItem :openSideNav="openSideNav" iconString="Home" />
                <SideNavItem :openSideNav="openSideNav" iconString="Add Video" />
                <SideNavItem :openSideNav="openSideNav" iconString="Delete Video" />
                <div class="border-b border-b-gray-700 my-2.5"></div>
                <SideNavItem :openSideNav="openSideNav" iconString="Subscriptions" />
                <SideNavItem :openSideNav="openSideNav" iconString="Library" />
                <SideNavItem :openSideNav="openSideNav" iconString="Liked" />
                <SideNavItem :openSideNav="openSideNav" iconString="History" />
                <SideNavItem :openSideNav="openSideNav" iconString="Watch Later" />
                <div v-if="openSideNav">
                    <div class="border-b border-b-gray-700 my-2.5"></div>
                    <div class="text-gray-400 text-[14px] text-extrabold">
                        About Press Copyright
                        <div>Contact us</div>
                        Creator Advertise Developers
                    </div>
                    <div class="border-b border-b-gray-700 my-2.5"></div>
                    <div class="text-gray-400 text-[14px] text-extrabold">
                        Terms Privacy Policy & Safety
                        <div>How YouTube works</div>
                        <span>Test new features</span>
                    </div>
                </div>
            </ul>
        </div>
        <div id="SideNavOverlay">
        
        </div>
        <slot />
    </div>
</template>
