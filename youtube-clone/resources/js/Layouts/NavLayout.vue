<script setup>
import { ref } from 'vue';
import { Link } from '@inertiajs/vue3';
import MenuIcon from 'vue-material-design-icons/Menu.vue';
import MagnifyIcon from 'vue-material-design-icons/Magnify.vue';

</script>

<template>
    <div class="relative">
        <div id="TopNav" class="w-[100%] h-[60px] fixed bg-black z-20 flex items-center justify-between">
            <div class="flex items-center">
                <button class="p-2 ml-3 rounded-full hover:bg-gray-800 inline-block cursor-pointer">
                    <MenuIcon fillColor="#FFFFFF" :size="26" />
                </button>
                <div class="mx-2"></div>
                <div class="flex text-white items-center justify-center mr-10 cursor-pointer">
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
                    class="rounded-full mx-8"
                    width="35"
                    src="https://yt3.ggpht.com/yti/AHyvSCAFJ6g9MbHJKTba65j-9N4ZPPkODN5_VnFGkez5=s88-c-k-c0x00ffffff-no-rj-mo"
                />
            </div>
        </div>
        <div id="SideNav">
        
        </div>
        <div id="SideNavOverlay">
        
        </div>
        <slot />
    </div>
</template>
