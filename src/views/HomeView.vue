<template>
  <div class="grid grid-cols-2 md:grid-cols-4 absolute center place-content-center bg-white w-full pt-5 pb-5 md:p-10 gap-5 md:gap-10">
    <div class="bg-t1 p-2 md:p-7 col-span-2 md:col-span-1 text-center rounded-2xl flex md:flex-col sticky h-full md:overflow-hidden overflow-x-scroll gap-2">
      <h1 class="p-4 bg-t6 hover:bg-t2 rounded-xl">คำคม</h1>
      <h1 class="p-4 bg-t6 hover:bg-t2 rounded-xl">ตลก</h1>
      <h1 class="p-4 bg-t6 hover:bg-t2 rounded-xl">หนัง</h1>
      <h1 class="p-4 bg-t6 hover:bg-t2 rounded-xl">หนังสือ</h1>
      <h1 class="p-4 bg-t6 hover:bg-t2 rounded-xl">อาหาร</h1>
      <h1 class="p-4 bg-t6 hover:bg-t2 rounded-xl">เกม</h1>
    </div>
    <div class="bg-config col-span-2 md:col-span-3 relative ">
      <div class="overflow-y-scroll scrollbar h-config m-auto p-5">
        <div v-for="user in user" :key="user" class=" pt-5 pb-5 rounded-xl md:w-4/6 mt-5 mb-5 overflow-hidden m-auto  bg-transparent">
          <div class="flex gap-3 justify-between pl-5 pr-5">
            <h1>{{user.username}}</h1>
            <h2>{{user.date}}</h2>
          </div>
          <div class="h-0.5 w-full bg-black mt-3 mb-5"></div>
          <img class="w-11/12 overflow-hidden rounded-2xl m-auto " :src="user.img" alt="">
        </div>
      </div>
      <div @click="addContent" class="absolute bg-t1 -right-4 -bottom-4 p-3 rounded-full hover:cursor-pointer">
        <img class="w-7 " :src="add" alt="add">
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import add from '@/assets/image/add.png';
import defaultImg from '@/assets/image/default-image.jpg';

export default {
  name: 'HomeView',
  components: {
  },
  data() {
    return {
      add,
      defaultImg,
      user: [
      {
        username: "test-user",
        date: "2020-01-02",
        img: defaultImg,
      },
      {
        username: "test-user",
        date: "2020-01-01",
        img: defaultImg,
      },
      {
        username: "test-user",
        date: "2019-12-23",
        img: defaultImg,
      },
      ]
    }
  },
  methods: {
    addContent() {
      this.$router.push('/add-content');
    }
  }
}
</script>

<style scoped>
  .scrollbar::-webkit-scrollbar{
    width: 1.5rem;
  }

  .scrollbar::-webkit-scrollbar-track {
    background-color: #F8AD9D;
    border-radius: 2rem;
    margin-block: 0.5rem;
  }

  .scrollbar::-webkit-scrollbar-thumb {
    background-color: #D16565;
    border: 5px solid #F8AD9D;
    border-radius: 2rem;
  }

  .scrollbar::-webkit-scrollbar-thumb:hover {
    background-color: #FFDAB9;
  }

  .bg-config {
    background: linear-gradient(180deg, #FFDAB9 0%, #F8AD9D 45.83%, #F4978E 100%);
    backdrop-filter: blur(20px);
    border-radius: 20px;
  }
  template{
    background: #ffffff;
  }
  .contact{
    background: linear-gradient(155.24deg, rgba(255, 255, 255, 0.4) 1.56%, rgba(255, 255, 255, 0.1) 92.44%);
    box-shadow: -4px 9px 24px 1px rgba(0, 0, 0, 0.2);
    border-radius: 40px;
  }
  .bg-transparent{
    background: linear-gradient(155.24deg, rgba(255, 255, 255, 0.4) 1.56%, rgba(255, 255, 255, 0.1) 92.44%);
  }

  .h-config{
    height: calc(100vh - 9rem);
  }
</style>