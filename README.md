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

## 그럼 대체 왜 이렇게 사용하는 걸까요?
비교를 해보면 왜 이런 방식으로 사용하는지 좀더 이해가 될것입니다. 

위의 코드를
``` html
<div class="element" :class="{ red : true, large:true}"  v-on:click=" fontLarge= !fontLarge"> This is content</div>
<div class="element" :class="{ red : true, large:false}"  v-on:click=" large= !large"> This is content</div>
```   
그리고 
``` javascript
return {
   redColor: false,
   fontLarge : true
   }
스타일태그에 추가하세요
.large { font-size: 30px;}
``` 
브라우저의 개발자도구 > 엘리먼트탭에서 확인해보면,   
<img width="390" alt="스크린샷 2023-03-12 오후 1 16 25" src="https://user-images.githubusercontent.com/48478079/224524003-04fcdd47-f8cd-42c8-b844-97f9ea9c0e2c.png">



