<script setup>
import RockButon from './gameButtons/RockButon.vue';
import PaperButon from './gameButtons/PaperButon.vue';
import Scissors from './gameButtons/Scissors.vue';
</script>

<template>

        <div>
            <h2 class="text-2xl font-semibold ">Choose your moove :</h2>
            <div  id="btnContainer" class="mt-2 mb-4 flex justify-center gap-4">
                <rock-buton/>
                <paper-buton/>
                <scissors/>
            </div>
        </div>

</template>

<style scoped></style>