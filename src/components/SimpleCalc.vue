<template>
  <div class="container">
    <div class="calc">
     
      <div class="result">
        <p>{{ result || 0 }}</p> <p>{{ resultcalc }}</p>
      </div>
    <div class="number">
    <div class="row-1">
      <button @click="clear">AC</button>
      <button @click="del">DEL</button>
      <button @click="percent">%</button>
      <button @click="append('/')">/</button>

    </div>
    <div class="row-2">
      <button @click="append('7')">7</button>
      <button @click="append('8')" >8</button>
      <button @click="append('9')" >9</button>
      <button @click="append('*')">*</button>
    </div>
    <div class="row-3">
      <button @click="append('4')" >4</button>
      <button @click="append('5')" >5</button>
      <button @click="append('6')" >6</button>
      <button @click="append('-')">-</button>
      </div>
    <div class="row-4">
      <button @click="append('1')">1</button>
      <button @click="append('2')">2</button>
      <button @click="append('3')"  >3</button>
      <button @click="append('+')">+</button>
      </div>
    <div class="row-5">
      <button @click="append('00')" >00</button>
      <button @click="append('0')"  >0</button>
      <button @click="dot">,</button>
      <button @click="calc">=</button>
    </div>
    </div>
    
  </div>
  </div>
</template>
  
<script>
export default {
data(){
  return{
    resultcalc:'',
    result:'',
    previos:'',
  }
},
methods: {
  clear(){
    this.result=''; 
    this.resultcalc='';

  },
  del(){
    this.result=this.result.slice(0,-1);
    },
  calc(){
    this.previos = this.result ;
    this.resultcalc=eval(`${this.result}`);
    this.calc=this.resultcalc
  },
  percent(){
    this.result=`${parseFloat(this.result)/100}`;
  },
  append(num){
     this.result = this.result + num;
  },
  dot(){
    if (this.result.indexOf(',') === -1){
      this.append(',');
    }
  },
 }
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  background-color: rgb(23, 34, 59);
  font-family: tahoma;

}
button{
  cursor: pointer;
}
.container{
 width: 100%;
 height: 100%;
}
.calc{
  border: 1px solid rgb(30, 30, 253);
  border-radius: 7px;
  width: 350px;
  height:560px;
  margin: 0 auto;
  display: flex ;
  flex-direction:column ;
  justify-content: flex-start;
  align-items: center;
  gap:7px;
  background-color: rgb(10, 15, 27);

}
.result{
  display: flex ;
  justify-content:  flex-end;
  align-items:  flex-end;
  border-radius: 7px;
  width: 335px;
  height: 170px;
  margin: 7px 7px;
  background-color:rgb(23, 34, 59) ;
}
.result p{
  color:#fff;
  font-size: 2.5rem;
  font-weight: 400;
  padding: 10px;
}
.number{
  width:340px;
  height:368px;
  border-radius: 7px;
  background-color: rgb(10, 15, 27);
  
}
.number .row-1{
  background-color: rgb(10, 15, 27);
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 0px 5px;
  
}
.number .row-1 button{
  width:75px ;
  height:65px;
  border: none;
  background-color:rgb(23, 34, 59) ;
  border-radius:7px;
  color:#fff;
  font-size: 1.8rem;
  font-weight: 400;
  transition: all 0.2s ease-in;

}
.number .row-1 button:hover{
  background-color:rgb(59, 87, 153) ;
  border: 1px solid rgb(30, 30, 253) ;
}
.number .row-2{
  background-color: rgb(10, 15, 27);
  display: flex;
  justify-content: space-between;
  align-items: center;
  /* margin-top: 7px; */
  margin: 7px 5px;

}
.number .row-2 button{
  width:75px ;
  height:65px;
  border: none;
  background-color:rgb(23, 34, 59) ;
  border-radius:7px;
  color:#fff;
  font-size: 1.8rem;
  font-weight: 400;
  transition: all 0.2s ease-in;
}
.number .row-2 button:hover{
  background-color:rgb(59, 87, 153) ;
  border: 1px solid rgb(30, 30, 253) ;
}
.number .row-3{
  background-color: rgb(10, 15, 27);
  display: flex;
  justify-content: space-between;
  align-items: center;
  /* margin-top: 7px; */
  margin: 7px 5px;

}
.number .row-3 button:hover{
  background-color:rgb(59, 87, 153) ;
  border: 1px solid rgb(30, 30, 253) ;
}
.number .row-3 button{
  width:75px ;
  height:65px;
  border: none;
  background-color:rgb(23, 34, 59) ;
  border-radius:7px;
  color:#fff;
  font-size: 1.8rem;
  font-weight: 400;
  transition: all 0.2s ease-in;

}
.number .row-4{
  background-color: rgb(10, 15, 27);
  display: flex;
  justify-content: space-between;
  align-items: center;
  /* margin-top: 7px; */
  margin: 7px 5px;

}

.number .row-4 button{
  width:75px ;
  height:65px;
  border: none;
  background-color:rgb(23, 34, 59) ;
  border-radius:7px;
  color:#fff;
  font-size: 1.8rem;
  font-weight: 400;
  transition: all 0.2s ease-in;

}
.number .row-4 button:hover{
  background-color:rgb(59, 87, 153) ;
  border: 1px solid rgb(30, 30, 253) ;
}
.number .row-5{
  background-color: rgb(10, 15, 27);
  display: flex;
  justify-content: space-between;
  align-items: center;
  /* margin-top: 7px; */
  margin: 7px 5px;

}
.number .row-5 button{
  width:75px ;
  height:65px;
  border: none;
  background-color:rgb(23, 34, 59) ;
  border-radius:7px;
  color:#fff;
  font-size: 1.8rem;
  font-weight: 400;
  transition: all 0.2s ease-in;

}
.number .row-5 button:hover{
  background-color:rgb(59, 87, 153) ;
  border: 1px solid rgb(30, 30, 253) ;
}

</style>
