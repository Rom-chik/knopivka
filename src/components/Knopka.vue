<script setup lang="ts">
//import { onMounted } from "vue";

const props = defineProps< {
  label: string;
  onclick: Function;
  disabled: boolean
}>();

const onButtonClick = () => {
  if(!props.disabled) {
    props.onclick();
  }
}


</script>

<template>


      <div>
          <button @click="onButtonClick()" :disabled="props.disabled" class="disabled:cursor disabled:bg-white cursor bg-white border border-black rounded rotate-6 hover:bg-sky-100 enabled:hover:rotate-0 transition-all duration-75 ease-in-out">
            {{props.label}}
          </button>
      </div>


</template>

<style scoped>

</style>