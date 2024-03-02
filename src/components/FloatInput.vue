<script setup lang="ts">
import {computed} from "vue";

const props = defineProps< {
  modelValue: string;
  label: string;
  onclick: Function;
  error: boolean;
}>();

const emits = defineEmits(['update:modelValue']);

const modelValue = computed({
  get: () => props.modelValue,
  set: (value: string) => emits('update:modelValue', value)
});

const onButtonClick = () => {
    props.onclick();
};



</script>

<template>


  <div class="relative">
    <input v-model="modelValue" id="myInput" type="text" :class="{ ' !border-red-500 ': props.error }" class=" peer focus:outline-none border-2 border-black focus:border-sky-500 " placeholder=" "/>
    <label for="myInput" class="absolute left-1 -top-6 peer-placeholder-shown:top-0 peer-focus:-top-6 transition-all duration-75" >{{props.label}}</label>
  </div>
  <div>
    <button @click="onButtonClick()" class="border border-black hover:bg-[#69D9FF]">Check</button>
  </div>


</template>

<style scoped>

</style>