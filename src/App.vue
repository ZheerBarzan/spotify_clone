<script setup>
import { ref, } from 'vue';
import { RouterLink, RouterView } from 'vue-router';

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

                <button class="bg-black hover:bg-[#282828] rounded-full cursor-pointer p-0.5 mr-8 mt-0.5">
                  <div class="flex items-center">
                    <img src="../src/assets/spotify.png" alt="" class="rounded-full" width="27">
                  </div>
                </button>

    </div>
 </div>

  
</template>

