<script setup>
import {
  onMounted,
  ref,
} from 'vue';

let test = ref(5);
const myLoop = ref(['alpha', 'bravo', 'charlie']);
console.log(test);

onMounted(() => {
  test.value = 7;
});

const resetTextField = () => {
  test.value = '';
};
</script>

<template>
  <div>
    <input type="text" v-model="test" v-on:keyup.enter.space="resetTextField" />
    <button v-on:click="resetTextField">reset</button><br>
    {{ test }}
    <div v-if="test">
      Du har skrevet tekst
    </div>
    <div v-else>
      Du har ikke skrevet tekst, eller du har trykker space... Idiot
    </div>
    <hr>
    <ul>
      <li v-for="item in myLoop">
        {{ item }}
      </li>
    </ul>
  </div>
</template>
