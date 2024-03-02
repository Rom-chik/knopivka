<script setup lang="ts">
import Knopka from './components/Knopka.vue'
import FloatInput from './components/FloatInput.vue'
import StringOutput from './components/StringOutput.vue'
import {ref} from "vue";
import {computed} from "vue";

const inputValue = ref("");

const error = computed(() => {
  return inputValue.value.length <= 1;
})

const consoleLog = () => {
  console.log("Button was touched");
}
const showError = () => {
    console.log("wrong input")
}

</script>

<template>
  <div class="">

<!--header-->
    <div class="flex justify-center items-center w-full h-[40vh] text-9xl">
          I   n   c   -   D   e   v
    </div>


<!--middle components-->
      <div class="flex flex-wrap gap-10 justify-center items-center w-full h-[90vh] bg-gray-50">

            <div class="rounded-2xl bg-[#69D9FF] flex justify-center items-center w-1/6 h-1/2">

                  <div class="flex flex-col gap-5 justify-center items-center">
                      <Knopka label="тисни" :onclick="consoleLog" :disabled="false" />
                      <Knopka label="не тисни" :onclick="consoleLog" :disabled="true" />
                  </div>
            </div>

            <div class="rounded-2xl bg-[#8be78b] flex justify-center items-center w-1/6 h-1/2">
                  <div class="flex flex-col gap-5 justify-center items-center">
                        <FloatInput label="Username" v-model="inputValue" :onclick="showError" :error="error"/>
                  </div>
            </div>

            <div class="rounded-2xl bg-[#E8E88B] flex justify-center items-center w-1/6 h-1/2">
                  <div class="flex flex-col gap-5 justify-center items-center">
                      <StringOutput/>
                  </div>
            </div>
     </div>


<!--bottom side scroll-->
     <div class="flex gap-72 side-scroll items-center w-full h-[100vh]">
       <div class="pl-[300px] side-scroll-element w-[100vw]">
          <div class="grid grid-rows-2 grid-flow-col-dense gap-4 w-[61vw]">
                    <div class="row-span-3">
                        <img class="h-[640px]" src="../ai_photo.png" alt="first picture">
                    </div>
                    <div class="col-span-2">
                        <img class="h-[312px]" src="../ai_photo_1.png" alt="second picture">
                    </div>
                    <div class="row-span-2 col-span-2">
                        <img class="h-[312px]" src="../ai_photo_2.png" alt="third picture">
                    </div>
          </div>
       </div>
       <div class="side-scroll-element w-[100vw]">
           <div class="grid grid-rows-2 grid-flow-col gap-4 w-[58vw]">
                     <div class="col-span-2 row-span-1">
                       <img class="h-[312px]" src="../ai_ukr_forces.png" alt="third picture">
                     </div>
                     <div class="row-span-1 col-span-1">
                       <img class="h-[312px]" src="../3_shturmova.jpg" alt="up square picture">
                     </div>
                     <div class="col-span-2 row-span-1">
                       <img class="h-[312px]" src="../ai_mil_complex.png" alt="fourth picture">
                     </div>
                     <div class="row-span-1 col-span-1">
                       <img class="h-[312px]" src="../ukr_oboron_prom.jpg" alt="down square picture">
                     </div>
           </div>
       </div>
     </div>


  </div>
</template>

<style scoped>

    .side-scroll{
        display: flex;
        flex-wrap: nowrap;
        overflow: auto;
    }
    .side-scroll-element{
        flex: 0 0 auto;
    }

</style>