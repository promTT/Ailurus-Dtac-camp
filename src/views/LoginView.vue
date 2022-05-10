<template>
  <div class="flex flex-col w-2/4 md:w-1/4 absolute center p-10 gap-3 items-center text-center text-white bg-transparent mt-5">
    <h1 class="text-5xl mb-5">Login</h1>
    <div v-show="signUP" class="flex w-full flex-row justify-center gap-5 ">
      <input class="w-full h-10 rounded-md text-black pl-5" type="text" placeholder="name" v-model="name" />
      <input class="w-full h-10 rounded-md text-black pl-5" type="password" placeholder="surname" v-model="surname" @keyup.enter="login"/>
    </div>
    <input class="w-full h-10 rounded-md text-black pl-5" type="text" placeholder="Username" v-model="username" />
    <input class="w-full h-10 rounded-md text-black pl-5" type="password" placeholder="Password" v-model="password" @keyup.enter="login"/>
    <input v-show="signUP" class="w-full h-10 rounded-md text-black pl-5" type="password" placeholder="re-enter Password" v-model="repassword" @keyup.enter="login"/>
    <div class="flex w-full flex-row justify-center gap-5 ">
      <button class="p-3 text-xl button rounded-xl w-full" v-show="signUP == false" @click="login">Login</button>
      <button class="p-3 text-xl button rounded-xl w-full" @click="sign">{{ msgSign }}</button>
    </div>
    <p class="text-xs" >{{ message }}</p>
    <div v-show="signUP == false">
      <h1 @click="toggleSwitch">&lt;&lt;&lt;Note>>></h1>
      <p class="text-xs" v-show="switcher">Username is user and Password is user1234</p>
    </div>
  </div>

</template>

<script>
export default {
  data() {
    return {
      message: "Lörem ipsum vissa predon. Krosöngar renas multick. Kontravåfade vamening som beligen fassa. Messa transtologi vir att ber och sant. Rönav könskonträr till gybel monor tunera. Heterolig mer.",
      username: "",
      password: "",
      repassword: "",
      switcher: false,
      signUP: false,
      msgSign: "Sign up",
      user: [{
        username: "admin",
        password: "admin1234",
      },
      {
        username: "user",
        password: "user1234",
      }
      ],
    }
  },
  methods: {
    sign() {
      this.signUP = !this.signUP
      if (this.repassword != ""){
        if (this.password == this.repassword){
          alert("Sign up success");
          this.password = "";
          this.repassword = "";
        }else if (this.password == "" | this.username ==""){
          alert("Please enter username and password");
        }
        else {
          alert("Password not match");
        }
      }
    },
    login()  {
      let username = this.username;
      let crUsername = this .user[1].username;
      if (username == crUsername && this.password == this.user[1].password){
        alert("success!");
        this.$router.push('/')
      }
      else if (this.password == "" | this.username ==""){
        alert("Please enter username and password");
      }
      else {
        alert("Password not match");
        this.username = "";
        this.password = "";
      }
    },
    toggleSwitch() {
      let booleanTest = this.switcher;
      if (booleanTest == true) {
        this.switcher = false;
      } else {
        this.switcher = true;
      }
    },
  }
}
</script>

<style scoped>
  .center {
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  .bg-transparent {
    background: linear-gradient(155.24deg, rgba(255, 255, 255, 0.4) 1.56%, rgba(255, 255, 255, 0.1) 92.44%);
    box-shadow: -4px 9px 24px 1px rgba(0, 0, 0, 0.2);
    border-radius: 40px;
  }
  .button{
    background: linear-gradient(155.24deg, #F08080 1.56%, #FFDAB9 92.44%);
    mix-blend-mode: soft-light;
    box-shadow: 0px 0px 20px 9px rgba(0, 0, 0, 0.2);
  }
</style>