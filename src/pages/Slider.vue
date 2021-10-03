<template>
 <div class="flex flex-wrap w-full">
     <div v-for="colour,index in sliders" :key="(colour,index)" class="absolute w-full">
        <div v-if="currentSlide == index" 
            class="absolute w-full" 
            :class="colour"
            style="height:350px">
        </div>
     </div>
 
    
    <h1 class="w-full flex-wrap text-center text-3xl my-4">Slider</h1>
 </div>
</template>

<script>
export default {
    data(){    
        return{
            currentSlide: 0,
            sliders: ['bg-blue-500', 'bg-yellow-500','bg-pink-500'],
            interval: "",
        };
    },
    mounted(){
         this.interval = setInterval(() => {
             this.currentSlide = this.currentSlide === 2 ? 0 : this.currentSlide+1
            //  if (this.currentSlide === 2) {
            //      this.currentSlide = 0;
            //  } else {
            //      this.currentSlide++
            //  }
             
         }, 4000);
    },
    beforeUnmount(){
        clearInterval(this.interval);
    }
}
</script>

<style>

</style>