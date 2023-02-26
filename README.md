:cactus: Vue3 Lesson 

## + - *  / 계산기 만들기

```html
<h2>간단한 계산기</h2>
<div id="app">
  <p> <input v-model.number="num1">
  <input v-model.number="num2"> </p>
  <button v-on:click="addcal">덧샘계산</button>
  <button v-on:click="subcal">뺄샘계산</button>
  <button v-on:click="multical">곱샘계산</button>
  <button v-on:click="divcal">나눗샘계산</button>
  <p>결과는 {{ result }} 입니다.</p>
</div>

<script>
Vue.createApp({
data(){
  return { num1:0, num2:0, result:0 }
},
methods:{
addcal:function() { this.result = this.num1 +  this.num2; },
subcal:function() { this.result = this.num1 -  this.num2; },
multical:function() { this.result = this.num1 *  this.num2;},
divcal:function() { this.result = this.num1 / this.num2; }
}
}).mount("#app")
</script>
```

<img width="300" alt="스크린샷 2023-02-26 오후 9 06 55" src="https://user-images.githubusercontent.com/48478079/221409533-31f371b1-b99a-4152-9a97-c8f699d032fe.png">
