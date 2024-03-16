<script setup>
import { ref, } from 'vue';
import { RouterLink, RouterView } from 'vue-router';
import { MenuItem} from "./components/MenuItem.vue";

import cheveronUP from 'vue-material-design-icons/ChevronUp.vue';
import cheveronDown from 'vue-material-design-icons/ChevronDown.vue';
import cheveronLeft from 'vue-material-design-icons/ChevronLeft.vue';
import cheveronRight from 'vue-material-design-icons/ChevronRight.vue';

let openMenu = ref(false);
</script>

<template>

 <div>
    <div class="w-[calc(100%-240px)]
                h-[60px]
                fixed
                right-0
                z-20
                bg-[#101010]
                bg-opacity-80
                flex
                items-center
                justify-between">
                
                <div class="flex items-center ml-6">
                    <button type="button" class="rounded-full bg-black p-[1px] cursor-pointer">

                        <cheveronLeft :size="30" fillColor="white" />
                    </button>
                    <button type="button" class="rounded-full bg-black p-[1px] ml-4 cursor-pointer">

                    <cheveronRight :size="30" fillColor="white" />
                    </button>
                </div>

                <button 
                @click="openMenu = !openMenu" :class="openMenu ? 'bg-[#282828]' : 'bg-black'"
                
                class="bg-black hover:bg-[#282828] rounded-full cursor-pointer p-0.5 mr-8 mt-0.5">
                  <div class="flex items-center">
                    <img src="../src/assets/spotify.png" alt="" class="rounded-full" width="27">
                    <div class="text-white ml-1.5 text-[14px] font-semibold">Zheer Barzan</div>
                    <cheveronDown v-if="!openMenu" @click="openMenu = true" :size="20" fillColor="white" />
                    <cheveronUP v-else @click="openMenu = false" :size="20" fillColor="white" />
                  </div>
                </button>

                <span 
                 v-if="openMenu"
                 class="fixed w-[190px] bg-[#282828] shadow-2xl z-50 rounded-sm top-[52px] right-[35px] p-1 cursor-pointer"
                >
                <ul class="text-grey-200 font-semibold text-[14px]">
                  <li class="px-3 py-2 text-white hover:bg-[#3E3D3D] hover:text-green-500 border-b border-b-grey-600">Profile</li>
                  <li class="px-3 py-2 text-white hover:bg-[#3E3D3D] hover:text-red-500  ">Logout</li>

                </ul>

                </span>

    </div>

    <div 

    id="SideNav"
    class="h-[100%] p-6 w-[240px] fixed z-50 bg-black">
  
    <RouterLink to="/">
      <img src="/public/images/icons/spotify-logo.png" alt="" width="125">
    </RouterLink>

    <div class="my-8"></div>
    <ul>
      <RouterLink to="/">
        <MenuItem iconString="home" iconSize="20" name="Home" pageUrl="/"/>
    </RouterLink>

    </ul>
  
  </div>
 </div>

  
</template>

