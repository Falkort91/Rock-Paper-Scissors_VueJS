<script setup>
import {ref} from 'vue';

const name = ref('paper');
const emit = defineEmits(['paperMoove']);
const paperMoove = () => {emit('paperMoove', name);
    console.log('paper');
};

</script>

<template>
    <button  
        class="bg-blue-600 text-5xl p-2 rounded duration-300 hover:opacity-75 hover:cursor-pointer" 
        @click="paperMoove"
        >
        &#x270B;
    </button>
</template>

<style scoped>

</style>