<template>
 <div class="example">
  <!-- <img src="https://st2.depositphotos.com/4521519/7577/v/950/depositphotos_75770271-stock-illustration-old-chemistry-laboratory-pattern-set.jpg" /> -->
  <p>Co-Lab</p>
  <a button v-on:click="display">search</a>
  <b input type="text" name="text"></b>
 </div>
</template>

<script>
import {labdata} from "@/data/data.js"
export default {
  created: function () {
    // `this` は vm インスタンスを指します
    console.log('a is: ' + this.a)
  }

  
}
</script>

<style>
 .example {
  /* position: relative; */
    width: 100%;
    height: 100%;
    left: 0;
    position: absolute;
    background: url('https://st2.depositphotos.com/4521519/7577/v/950/depositphotos_75770271-stock-illustration-old-chemistry-laboratory-pattern-set.jpg') no-repeat center center;
    background-size: cover;
  }

.example .fas {/*classがfaのアイコンに対して*/
  position: absolute;
  top: 50%;
  left: 50%;
  -ms-transform: translate(-50%,-50%);
  -webkit-transform: translate(-50%,-50%);
  transform: translate(-50%,-50%);
  margin:0;/*余計な隙間を除く*/
  padding:0;/*余計な隙間を除く*/
  color: white;/*アイコン色*/
  font-size: 60px;/*サイズ*/
  }


.example p {
  position: absolute;
  color: white;/*文字は白に*/
  font-weight: bold; /*太字に*/
  font-size: 10em;/*サイズ2倍*/
  top: 30%;
  left: 50%;
  -ms-transform: translate(-50%,-50%);
  -webkit-transform: translate(-50%,-50%);
  transform: translate(-50%,-50%);
  margin:0;
  padding:0;
  /*文字の装飾は省略*/
  }

.example a {/*aタグを画像の真ん中に*/
  position: absolute;
  top: 50%;
  left: 60%;
  -ms-transform: translate(-50%,-50%);
  -webkit-transform: translate(-50%,-50%);
  transform: translate(-50%,-50%);
  /*以下装飾*/
  margin:0;/*余計な隙間を除く*/
  font-size: 25px;/*文字サイズ*/
  border: solid white 2px; /*線で囲う*/
  padding: 7px;/*文字と線の間の余白*/
  color: green;/*文字色*/
  text-decoration: none;/*下線を表示させない*/
  }

.example a:hover{/*カーソルを当てたとき*/
  background: rgba(255, 255, 255, 0.3);/*背景を半透明に*/
  }

.example img {
  width: 100%;
  }

</style>

