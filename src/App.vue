<template>
  <nav class="navbar shadow-lg">
    <div class="container mx-auto ">
      <div class="flex justify-between h-16 items-center">
        <router-link class="flex content-center gap-2 items-center" to="/"
          ><img class="h-12 p-0" :src="logo" alt="Logo"
        /><h1 class="text-2xl">Ailurus</h1></router-link>
        <div class="sm:self-center text-xl md:flex items-center hidden">
          <div class="sm:inline-block">
            <router-link class="p-3 hover:text-white" to="/"
              >Home</router-link
            >
          </div>
          <div class="sm:inline-block">
            <router-link class="p-3 hover:text-white" to="/contact"
              >Contact-us</router-link
            >
          </div>
          <div class="sm:inline-block">
            <router-link class="p-3 hover:text-white" to="/login"
              >Login</router-link
            >
          </div>
        </div>
        <div class="sm:self-center text-xl flex items-center md:hidden">
          <div class="flex flex-col gap-3" @click="toggleSwitch()">
            <div class="w-10 h-0.5 bg-t6 "></div>
            <div class="w-10 h-0.5 bg-t6 "></div>
            <div class="w-10 h-0.5 bg-t6 "></div>
          </div>
          <div  v-if="switcher" class="self-center text-xl block md:hidden absolute top-16 bg-t5 left-0 p-4 w-screen">
            <div class="sm:inline-block">
              <router-link class="p-3 hover:text-white" to="/"
                >Home</router-link
              >
            </div>
            <div class="sm:inline-block">
              <router-link class="p-3 hover:text-white" to="/contact"
                >Contact-us</router-link
              >
            </div>
            <div class="sm:inline-block">
              <router-link class="p-3 hover:text-white" to="/login"
                >Login</router-link
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </nav>
  <router-view/>
</template>

<script>
import logo from '@/assets/image/logo.png';

export default {
  name: 'HomeView',
  components: {
  },
  data() {
    return {
        logo: logo,
        switcher: false
    }
  },
  methods: {
    toggleSwitch() {
      let booleanTest = this.switcher;
      if (booleanTest == true) {
        this.switcher = false;
      } else {
        this.switcher = true;
      }
    },
  },
}
</script>

<style>
::selection {
  background: #FFFFFF;
}

::-moz-selection {
  background: #FFFFFF;
}

.text-main::selection {
  color: #cbccc6;
}
.text-main::-moz-selection {
  color: #cbccc6;
}

body {
  background-image: radial-gradient(circle, rgba(240, 128, 128, 1) 0%, rgba(255, 218, 185, 1) 100%);
  overflow-x: hidden;
}
.navbar {
  background-color: #FFDAB9;
  color: #D16565;
  padding-left: 30px;
  padding-right: 30px;
}
h1 {
  font-family: Consolas, monaco, monospace;
  font-size: 24px;
  font-style: normal;
  font-variant: normal;
  font-weight: 700;
  line-height: 26.4px;
}
h3 {
  font-family: Consolas, monaco, monospace;
  font-size: 14px;
  font-style: normal;
  font-variant: normal;
  font-weight: 700;
  line-height: 15.4px;
}
p {
  font-family: Consolas, monaco, monospace;
  font-size: 14px;
  font-style: normal;
  font-variant: normal;
  font-weight: 400;
  line-height: 20px;
}
blockquote {
  font-family: Consolas, monaco, monospace;
  font-size: 21px;
  font-style: normal;
  font-variant: normal;
  font-weight: 400;
  line-height: 30px;
}
pre {
  font-family: Consolas, monaco, monospace;
  font-size: 13px;
  font-style: normal;
  font-variant: normal;
  font-weight: 400;
  line-height: 18.5714px;
}
</style>
