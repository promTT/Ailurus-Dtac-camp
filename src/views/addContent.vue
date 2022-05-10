<template>
  <div class="bg-t2 p-5">
      <div class="grid grid-cols-5 gap-10 m-5">
          <div class="col-span-2 bg-t1 rounded-xl">
            <canvas width="400" height="400">
            </canvas>
          </div>
          <div class="col-span-3 bg-t1 rounded-xl">
            <textarea class="rounded-xl placeholder:text-t6 p-5" v-model="msg" placeholder="ระบายมาได้เลย" name="text" id="text" @click="random" @keyup="lineTo"></textarea>
          </div>
      </div>
      <input class="rounded-md m-5 mt-0 pl-0.5 mb-0 pr-0.5" type="color" v-model="color">
      <button class="rounded-md m-5 mt-0 p-2 mb-0 bg-t1 text-md" @click="clear">Clear</button>
  </div>
</template>

<script>

export default {
  data() {
    return {
      xCoordinate1: null,
      yCoordinate1: null,
      xCoordinate2: null,
      yCoordinate2: null,
      color: null,
      k: 0,
      msg: null,
    }
  },
  methods: {
    random() {
      this.xCoordinate1 = (Math.floor(Math.random() * 201) + Math.floor(Math.random() * 201));
      this.yCoordinate1 = (Math.floor(Math.random() * 201) + Math.floor(Math.random() * 201));
      this.xCoordinate2 = Math.floor(Math.random() * 401)
      this.yCoordinate2 = Math.floor(Math.random() * 401)
    },

    lineTo() {
      var i = 0
      while (i < 1) {
        const canvas = document.querySelector('canvas');
        const ctx = canvas.getContext('2d');
        ctx.beginPath();
        ctx.strokeStyle = this.color;
        ctx.moveTo(this.xCoordinate1, this.yCoordinate1);
        if(this.k%2 == 0) {
          var g = 1
        } else {
          g = -1
        }

        var xavg = ((this.xCoordinate1 + this.xCoordinate2) / 2) + (50 * g);
        var yavg = ((this.yCoordinate1 + this.yCoordinate2) / 2) + (50 * g);

        ctx.quadraticCurveTo(xavg, yavg, this.xCoordinate2, this.yCoordinate2);
        this.xCoordinate2 = this.xCoordinate1;
        this.yCoordinate2 = this.yCoordinate1;
        this.xCoordinate1 = (Math.floor(Math.random() * 201) + Math.floor(Math.random() * 201));
        this.yCoordinate1 = (Math.floor(Math.random() * 201) + Math.floor(Math.random() * 201));
        ctx.stroke();
        this.k = this.k + 1;
        i++
      }
    },

    clear() {
      const canvas = document.querySelector('canvas');
      const ctx = canvas.getContext('2d');
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      this.k = 0;
      this.xCoordinate1 = null;
      this.yCoordinate1 = null;
      this.xCoordinate2 = null;
      this.yCoordinate2 = null;
      this.msg = null;
    }
  },
}
</script>

<style scoped>

canvas{
  width: 100%;
  height: 100%;
}

textarea{
  width: 100%;
  height: 100%;
  background: #F08080;
  resize: none;
}

</style>