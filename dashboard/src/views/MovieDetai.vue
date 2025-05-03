<template>
    <div>
        <h1 class="text-gray-900 text-3xl font-bold " >
            Oppenheimer
        </h1>
    
    <div class="mt-11 flex flex-row items-center justify-between">
        <div class="flex flex-col space-y-3">
            <h2 class="text-gray-700 text-base font-bold uppercase">Director</h2>
            <p class="text-gray-600 text-xl font-semibold">Christopher Nolan</p>

        </div>
        <div class="flex flex-col space-y-3">
            <h2 class="text-gray-700 text-base font-bold uppercase">Release Date</h2>
            <p class="text-gray-600 text-xl font-semibold">21st July, 2023</p>

        </div>
    </div>
   
    <div v-if="currentStep==0">

  
    <div class="max-w-full mx-12 p-2 mt-7 bg-white shadow-2xl rounded">
        <img src="https://preview.redd.it/did-anyone-else-notice-that-v0-s9eh81pboeab1.jpg?auto=webp&s=1f1919e9cc70a90a9076e03f79924db0b10b6502" alt="Movie Poster">

    </div>
    <!-- <div class="w-full flex items-center justify-center mt-7 ">
        <button size="xl" variant="solid" color="" >Book tickets</button>
    </div> -->
    <div class="w-full flex items-center justify-center mt-7">
    <button class="px-6 py-3 text-white bg-black rounded-lg hover:bg-gray-800" @click="currentStep++">
        Book tickets
    </button>
</div>

    <div class="flex flex-col space-y-3 mt-16">
            <h2 class="text-gray-700 text-base font-bold uppercase">Synopsis</h2>
            <p class="text-gray-600 text-lg font-normal">The film is based on the Pulitzer Prize-winnning book American Prometheus</p>

        </div>  </div>
        <div v-else-if="currentStep==1">
            <h2 class="font-medium text-xl mt-7 text-gray-900">
                How many seats?
            </h2>
            <div class="flex flex-col w-full space-y-5 mt-6">
                <button  v-for="(index) in 8" class="px-6 mt-5 py-3 text-black bg-gray-10 rounded-lg hover:bg-gray-800 shadow-lg"
                size="lg" 
                
               :variant="
               index===bookingData.numberOfseats?'subtle':'white'
               "
                  @click=" setnumberofSeats(index)"
                >{{   index }}

                </button>
            </div>
        </div>
        
        <div class="flex flex-row mt-6 space-x-2">
            <button class="px-6 mt-25 py-3 text-black bg-gray-200 rounded-lg hover:bg-gray-800" v-if="currentStep!==0" @click="currentStep--"
      
        >
        Go Back
    </button>
    <button class="px-6 py-3 text-white bg-black rounded-lg hover:bg-gray-800" @click="currentStep++" 
    >
        Next
    </button>



        </div>
        
        
    
    
    
</div>

</template>
<script setup>
import {ref
    ,reactive
}

from "vue";  
const currentStep=ref(0);
const bookingData=reactive({
    numberOfseats:0,
    seats:[
    
] })
function  setnumberofSeats(n){
    bookingData.numberOfseats=n
}

</script>