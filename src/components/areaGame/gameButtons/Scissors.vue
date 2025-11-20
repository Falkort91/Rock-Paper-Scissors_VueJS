<script setup>
import {ref} from 'vue';

const name=ref('scissors');
const emit= defineEmits(['scissorsMoove']);
const scissorsMoove=()=>{emit('scissorsMoove',name);
    console.log('scissors');
};


</script>

<template>
    <button 
        class="bg-green-600 text-5xl p-2 rounded duration-300 hover:opacity-75 hover:cursor-pointer"
        @click="scissorsMoove"
        >
        &#x270C;
    </button>
</template>

<style scoped>

</style>