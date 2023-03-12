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

정상적으로 클래스가 들어간것처럼 보입니다. 이제 클릭이벤트를 발생시켜서 true <->false를 바꿔보도록 하겠습니다. 이 이벤트는 위에서 했던 빨간배경을 삽입또는 삭제하는 방식과 동일한데 <b> 작동하지 않습니다 </b> 그쵸! 여기까지 따라오셨나요 ?   
여기서 ```<style>``` 태그를 보겠습니다.  style태그의 .large는 ``` { font-size: 30px;}  ```로 설정되어 있습니다. 그러니까 .large가 true 일때는 클래스가 정상적으로 적용되지만 이벤트로 해당 클래스를 제거하는것은 되질 않습니다.   

이제 아래처럼 변경해보겠습니다  
```  
<div class="element" :class="{ red : redColor, large:!fontLarge}"  v-on:click=" redColor = !redColor"> 
   This is content</div>
<div class="element" :class="{ red : redColor, large:fontLarge}"  v-on:click=" fontLarge = !fontLarge"> 
This is content</div>
```   
어디가 바뀌었는지 알아보시겠습니까 ?
클래스 large의 여부를 data문의 return문에서 바꾸도록 변경했습니다.  이 예제는 작동이 매끄럽지 않아도 색상과 글자크기를 바뀌는 것에 중심을 둔 예제이니 이것만 잘 작동하는지 확인하시면 됩니다.    

간략하게 정리를 하자면,   
맨위에 있는 형식에서   ``` :class="{ 클래스이름: 조건}"  ``` 클래스를 삽입/삭제하는 ``` 조건 ```이 뒤따라오는데 이 ``` 조건 ```을 이벤트로 조정하려면 ``` 조건 ```을 data문에 선언해야 한다는 것입니다.  





