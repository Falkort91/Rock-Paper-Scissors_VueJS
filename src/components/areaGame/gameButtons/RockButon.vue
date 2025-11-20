<script setup>
import {ref} from 'vue';

const name = ref('rock');
const emit = defineEmits(['rockMoove']);
const rockMoove = () => {emit('rockMoove', name);
    console.log('rock');
};

</script>

<template>
    <button 
        class="bg-red-600 text-5xl p-2 rounded duration-300 hover:opacity-75 hover:cursor-pointer"
        @click="rockMoove"
        >
        &#x270A;
    </button>
</template>

<style scoped>

</style>