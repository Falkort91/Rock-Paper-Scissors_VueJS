<script setup>
const props = defineProps({data: Object})
</script>

<template>

    <slot ></slot>
    <p class="text-2xl font-semibold">Your score : <span class="text-blue-500"> {{props.data.userScore ? props.data.userScore : 0}} </span> - Computer score : <span class="text-red-500"> {{props.data.computerScore ? props.data.computerScore:0}} </span></p>
        

</template>

<style scoped></style>