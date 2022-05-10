<template>
  <div class="flex gap-2 items-center p-10 relative flex-col-reverse sm:flex-row">
    <div class="flex gap-2 md:w-9/12 w-full h-config overflow-y-scroll ">
      <div class="flex flex-col w-full gap-1 -translate-y-3/4">
        <div v-for="img in img" :key="img" class=" md:w-5/6  m-auto">
          <img class="h-full w-full overflow-hidden rounded-xl" :src="img" alt="">
        </div>
      </div>
      <div class="flex flex-col w-full gap-1 -translate-y-2/4">
        <div v-for="img in img" :key="img" class=" md:w-5/6  m-auto">
          <img class="h-full w-full overflow-hidden rounded-xl" :src="img" alt="">
        </div>
      </div>
      <div class="flex flex-col w-full gap-1 -translate-y-3/4">
        <div v-for="img in img" :key="img" class=" md:w-5/6  m-auto">
          <img class="h-full w-full overflow-hidden rounded-xl" :src="img" alt="">
        </div>
      </div>
    </div>
    <div class="w-full md:w-3/12 ml-5">
      <h1 class="text-7xl md:text-8xl font-black text-white">WHAT YOU LIKE</h1>
    </div>
    <div class="absolute right-3 bottom-3 p-1 pl-3 pr-3 bg-t1 rounded hover:rounded-xl" @click="home">
      <h1>Next</h1>
    </div>
  </div>
</template>

<script>
import defaultImg from '@/assets/image/default-image.jpg';

export default {
  data() {
    return {
      img: [defaultImg, defaultImg, defaultImg,defaultImg,defaultImg,defaultImg,defaultImg,defaultImg,defaultImg,defaultImg,defaultImg,defaultImg,defaultImg,defaultImg,]
    };

  },
  methods: {
    home() {
      this.$router.push('/');
    }
  }
}
</script>

<style scoped>
  .h-config{
    height: calc(100vh - 9rem);
  }
  ::-webkit-scrollbar{
    width: 0 ;
  }
  img:hover{
    outline: solid 0.2em #D16565;
  }

</style>