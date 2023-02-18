<template>
 
  <div class="container">
    <h2 class="title">My Simple Calculator</h2>
    <div class="calc">
    <div class="number">
     <input type="number" class="input" v-model=number1  />
     <input type="number" class="input" v-model=number2 />
     <div class="result">{{ result || '0' }}</div>
    </div>
     <div class="operator">
      <input type="button"  value="C" class="btn" @click="clear" />
      <input type="button"  value="+" class="btn" @click="sum" />
      <input type="button"  value="-" class="btn" @click="sub"/>
      <input type="button"  value="*" class="btn" @click="mult"/>
      <input type="button"  value="/" class="btn" @click="div"/>
     </div>
    </div>
  </div>
</template>
  
<script>
export default {
data(){
  return{
    result:'',
    number1:null,
    number2:null,
  }
},
methods: {
  clear(){
    this.result=''; 
    this.number1='';
    this.number2='';
  },
  sum(){
     this.result= this.number1|this.number2;   
  },
  sub(){
    this.result= this.number1-this.number2;
  },
  mult(){
    this.result= this.number1*this.number2;
  },
  div(){
    this.result= this.number1/this.number2;
  },
 }
}
</script>

<style>
.title{
  padding: 20px;
  color: rgba(150, 83, 44, 0.904);
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
  font-size: 3.5rem;
}
.number{
margin-top: 50px;
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
gap: 25px;
}
.calc{
display: flex;
justify-content: center;
align-items: center;
gap:50px;
}
.input{
 padding: 10px 100px;
 border: 1px solid rgb(177, 111, 56);
 border-radius: 7px;
 color: rgb(177, 111, 56);
}
.operator{
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
gap: 2px;
}
.btn{
  width:50px;
  padding: 10px;
  background-color: rgb(177, 111, 56) ;
  border: none;
  border-radius: 7px;
  font-size: 1.5rem;
  cursor: pointer;
  color: rgb(255, 225, 186);
}
.result{
  border: 1px solid rgb(177, 111, 56);
  border-radius: 7px;
  padding: 10px 50px;
  color:rgb(177, 111, 56) ;
}
</style>
