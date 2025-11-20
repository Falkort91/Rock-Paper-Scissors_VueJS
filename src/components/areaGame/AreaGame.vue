<script setup>
import RockButon from './gameButtons/RockButon.vue';
import PaperButon from './gameButtons/PaperButon.vue';
import Scissors from './gameButtons/Scissors.vue';
import {ref, computed} from 'vue';

const userChoice = ref(null);
const computerChoice=ref(null);
let randomNb = ref(0);
const userScore = ref(0);
const computerScore = ref(0);
const resultSentence= ref(null);

const computerMoove = computed(()=>{
    switch (randomNb.value) {
        case 1:
            computerChoice.value='rock';
            break;
        case 2:
            computerChoice.value='paper';
            break;
        case 3:
            computerChoice.value='scissors';
            break;
    
        default:
            break;
    }
    return computerChoice.value;
});

const playGame = (data)=>{
    userChoice.value = data.value;
    randomNb.value = Math.floor(Math.random()*3+1);
    computerChoice.value = computerMoove.value;
    console.log(randomNb.value,userChoice.value,computerChoice.value);

    if(userChoice.value === computerChoice.value){
        resultSentence.value = `It's a tie ! : <span class="text-blue-500"> ${userChoice.value}</span> / <span class="text-red-500"> ${computerChoice.value}</span> !` 
    }else if(
        (userChoice.value === 'rock' && computerChoice.value ==='scissors')||
        (userChoice.value === 'paper' && computerChoice.value ==='rock')||
        (userChoice.value === 'scissors' && computerChoice.value ==='paper'))
        { 
            resultSentence.value = `You win ! : <span class="text-blue-500"> ${userChoice.value}</span> beat <span class="text-red-500"> ${computerChoice.value}</span> !` ;
            userScore.value++;
    }else{
        resultSentence.value = `Looser ... : <span class="text-blue-500"> ${userChoice.value}</span> is beaten by <span class="text-red-500"> ${computerChoice.value}</span> !` ;
        computerScore.value++;
    }
    
}

const emit= defineEmits((['results']));
const sendResult=()=>{ 
    emit('results', {userScore:userScore.value,computerScore:computerScore.value,resultSentence:resultSentence.value});
};
</script>

<template>

        <div>
            <h2 class="text-2xl font-semibold ">Choose your moove :</h2>
            <div class="mt-2 mb-4 flex justify-center gap-4">
                <rock-buton @rock-moove="playGame" @click="sendResult"/>
                <paper-buton @paper-moove="playGame" @click="sendResult"/>
                <scissors @scissors-moove="playGame" @click="sendResult"/>
            </div>
        </div>

</template>

<style scoped></style>