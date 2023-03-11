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
    <div :class="[ 1>2 ? ' ' : 'style3']">파란 또는 녹색</div>
    <div :class="{style4 : true}"> 분홍색</div>

    <div :style="{ color: myRed }"> 빨간색으로  </div>
    <div :style="myOrange">보라색으로</div>
    <div :style="{color:anyColor}">겨자색</div>
    <div :style="colorntext">파란색</div>
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
