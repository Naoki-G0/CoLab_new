<template>
 <div class="example">
  <!-- <img src="https://st2.depositphotos.com/4521519/7577/v/950/depositphotos_75770271-stock-illustration-old-chemistry-laboratory-pattern-set.jpg" /> -->
  
  <p>Co-Lab</p>

  <form method="get" action="http://localhost:3000/result">
  <input type="text" id="name" name="name" placeholder="Freeword" autocomplete="off" required
       minlength="1" maxlength="25" size="30">
  </form>
  <NLink to="/result?category=生物学" tag="button">生物学</NLink>
  <NLink to="/result?category=物理学" tag="button">物理学</NLink>
 </div>
</template>

<script>
import {labdata} from "@/data/data.js"
export default {
  created: function() {
    // `this` は vm インスタンスを指します
    console.log('a is: ', labdata)

    const filteredLabdata = labdata.filter((l) => l.category === "生物学")
    console.log('a is: ', filteredLabdata)
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

.example a:hover{/*カーソルを当てたとき*/
  background: rgba(255, 255, 255, 0.3);/*背景を半透明に*/
  }

.example img {
  width: 100%;
  }

label {
    display: block;
    font: 1rem 'Fira Sans', sans-serif;
}

input,
label {
    position: absolute;
    top: 45.3%;
    left: 30%;
    margin: .4rem 0;
    border: solid black 2px; /*線で囲う*/
    font-size: 33px;/*文字サイズ*/
    background-color:white;
    color: black;/*文字色*/
}


</style>