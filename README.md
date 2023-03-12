##### 🌵 Vue3.js

## Vue에서 class를 적용하는 방법을 알아보겠습니다.

1. 객체(Object) 형태로 
``` :class="{ 클래스이름: 조건}"  ```
2. 배열(Arrary) 형태로
``` :class=" [ 조건? '클래스이름1' :'클래스이름2']"  ```
3. 인라인 스타일로 바인딩
``` <div :style={   }  ``` 


아래 예제를 잘 살펴보세요. 
``` html

<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <meta http-equiv="X-UA-Compatible" content="ie=edge">
   <script src="https://unpkg.com/vue@next"></script>
   <title>Document</title>
</head>
<body>
<div id="app">
    <div class="orange">오렌지색으로</div>
   
    <div :style="myOrange">보라색으로</div>
    <div :style="colorntext">파란색</div>
    <div :style="{ color: myRed }"> 빨간색으로  </div>
    <div :style="{color:anyColor}">겨자색</div>
   
    <div :class="[ 1>2 ? ' ' : 'style3']">파란 또는 녹색</div>
    <div :class="{style4 : true}"> 분홍색</div>
</div>
</body>
<script> 
Vue.createApp({
  data(){
    return {
      myRed :'red',
      myOrange:{
        fontSize: '30px',
        color :'purple'
      },
      colorntext:{
        textDecoration : 'underline',
        color:'blue'
       },
      anyColor:'gold'
    }   
}
}).mount("#app")
</script>
<style>
  .style3 { color:green}
  .style4 { color:pink}
</style>
</html>
```

## 예제를 해보겠습니다.

``` html
<div id="app">
     <div class="element" :class="{ red : true}" > This is content</div>
     <div class="element" :class="{ red : redColor}"> This is content</div>
</div>
  <script>
Vue.createApp({
  data(){
    return {
      redColor: false
    }
  }
}).mount("#app")
  </script>
  <style>
    div { margin: 10px;}
    .element { color:gold}
    .red { background-color: red;}
  </style>
```
여기서에서 return문의 redColor:true로 바꾸면 빨간배경에 노란색글자가 2줄 나옵니다. 하나는 style태그로 인해, 다른 하나는 return문의 속성지정으로 인해서 입니다.   
여기에 클릭이벤트를 넣어서 속성의 값을 바꾸는걸 해보겠습니다.  

``` <div class="element" :class="{ red : redColor}" v-on:click="redColor = !redClass"> This is content</div> ```  
      
return문의 redColor:false 로 되어 있는지 확인하세요. 2번째줄을 클릭하면 빨간배경에 노란글자가 나오는지 확인하세요.




