<script>
import { ref, toRefs, watchEffect} from 'vue';

import{ useRoute} from 'vue-router';

const route = useRoute();

const props = defineProps({
    iconString : String,
    iconSize : Number,
    pageUrl: String,
    name : String,
});

const {iconString, iconSize, pageUrl, name} = toRefs(props);


let icon = ref(null);
let textisHovered = ref(false);


watchEffect(() => {
    if(route.path== pageUrl.value){
        icon.value = iconString.value + '-active';
        textisHovered.value = true;
    }else {
        icon.value = iconString.value + '-inactive';
        textisHovered.value = false;
    }
});

const isHover = () =>{
    if (icon.value ===iconString.value + '-active'){ return;}

    if (icon.value ===iconString.value + '-inactive') {
        icon.value = iconString.value + '-inactive-hover';
        textisHovered.value = true;

    }else{
            icon.value = iconString.value + '-inactive';
            textisHovered.value = false;
        }

        
    
}


</script>



<template>

<li class="flex items-center justify-start pb-4 cursor-pointer"
@mouseenter="isHover()"
@mouseleave="isHover()"


>

<img :src="`/public/images/icons/${icon}.png`" :width="iconSize" >

<div :class="textisHovered ? 'text-white' : 'text-gray-400'"
class="ml-4 text-[14px] font-semibold mt-0.5"
></div>


</li>

</template>


<style scoped>
</style>