<template>
<div class= "contact text-center flex flex-col items-center gap-3 m-16 p-10 shrink text-white min-h-3/4">
    <img :src="logo" class="w-2/12" alt="logo">
    <h1 class="text-6xl color font-black">Ailurus</h1>
    <p class="text-base">{{contact}}</p>
</div>
</template>

<script>
// @ is an alias to /src
import logo from '@/assets/image/logo.png';

export default {
  name: 'conrtactUs',
    data() {
        return {
            logo: logo,
            contact: "เมื่อความรู้สึกของเราถูกระบายผ่านการพิมพ์ โดยมีความหลากหลายของความรู้สึกที่กลั้นออกมาเพื่อทำให้ผ่อนคลายความในใจในอารมณ์นั้น การสื่อสารวิธีนี้เป็นอีกหนึ่งตัวกลางความรู้สึกต่อบางสิ่งที่ต้องการเล่าผ่านตัวอักษร เพื่อสื่อสารให้ตัวเองหรือกลุ่มคนทราบจุดประสงค์ของความคิดหรือความรู้สึกของคนสื่อสาร แต่ถ้าหากเราอยากเปลี่ยนความรู้สึกที่เราระบายผ่านการสื่อสารทางตัวอักษรเป็นพลังงานแห่งศิลปะ คงตื่นเต้นไปพร้อมกับการคาดเดารูปร่างศิลปะผ่านความรู้สึกที่ได้สื่อสารแห่งความตั้งใจที่จะแสดงออกมา เป็นอีกหนึ่งที่ Ailurus ตั้งใจให้สุนทรียภาพกับความรู้สึกของคุณที่พร้อมจะผ่อนคลายไปกับศิลปะที่ได้รับ",
        };
    }
}
</script>

<style scope>
.contact{
    background: linear-gradient(155.24deg, rgba(255, 255, 255, 0.4) 1.56%, rgba(255, 255, 255, 0.1) 92.44%);
    box-shadow: -4px 9px 24px 1px rgba(0, 0, 0, 0.2);
    border-radius: 40px;
}

</style>
