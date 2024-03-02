<script setup lang="ts">
import {ref} from "vue";
import {computed} from "vue";

const userInput = ref('')

const userInputWithCharsOnly = computed( () => {
  let newString = '';
  for(let i = 0; i < userInput.value.length; i++ ){
    if(userInput.value.charCodeAt(i) > 57 || userInput.value.charCodeAt(i) < 48 ){
      newString += userInput.value.charAt(i);
    }
  }
  return newString;
})

/*const userInputWithCharsOnly = computed( () => {
  let newString = '';
  for(let i = 0; i < userInput.value.length; i++ ){
    if(  ){
      newString += userInput.value.charAt(i);
    }
  }
  return newString;
})*/

const userInputWithoutNumbers = computed( () => {

  const regex = /[0-9]/g;
   return userInput.value.replace(regex, '');

})

</script>


<template>
  <div>
        <input type="text" v-model="userInput" class="border border-black"/>
  </div>
  <div>
        {{ userInput }}
  </div>
  <div>
        {{ userInputWithCharsOnly }}
  </div>
  <div>
    {{ userInputWithoutNumbers }}
  </div>
</template>



<style scoped>

</style>