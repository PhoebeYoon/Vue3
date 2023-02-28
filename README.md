:cactus: Vue3 Lesson 


## 책정보 예제에 마우스 이벤트와 매개변수를 가진 함수의 실행까지 추가해보자

실습 1.
``` html
<style>
.box { padding: 100px 0; width: 40%; text-align: center;
    background-color: #ddd; margin: 20px; display: inline-block;}
</style>

<div id="app">
  <p v-if=showBook>
    {{title}} - {{author}} -{{pages}}
  </p>
  <button v-on:click="toggleShowBook">
    <span v-if="showBook">책정보감추기</span>
    <span v-else>책정보  보기</span>
  </button>
  <br>
  <!-- mouse events -->
  <div class="box" @mouseover="dealwithEvent">mouseover</div>
  <div class="box" @mouseleave="dealwithEvent">mouseleave</div>
  <div class="box" @dblclick="dealwithEvent">double click</div>
  <div class="box"></div> 
</div>
<script>
Vue.createApp({
data(){
  return {
    showBook :true,
      title :'The Load of Rings',
      author :'J. R. R. 톨킨',
      pages : '3권짜리 1볼륨'
    }
},
methods :{
  toggleShowBook(){
    this.showBook = !this.showBook
  },
  dealwithEvent(){
    console.log('okay')
  }
}
}).mount('#app');
</script>

```
실습 2.
```javascript

 dealwithEvent(e){
    console.log(e.type)
  }
```
위의 실습1 에서 자바스크립트 부분만 바꿔보자. 이벤트의 종류가 콘솔창에 출력되는지 확인해보자.

실습 3. 
아래와 같이 변경한 뒤에 출력결과를 확인해 보면 콘솔창에    
``` 100 undefined ```가 출력되어 이벤트를 인식하지 못한다. 
```html
 <div class="box" @mouseover="dealwithEvent(100)">mouseover</div>
 
  dealwithEvent(e){
    console.log(e, e.type)
    }
````
그래서, 아래와 같이 변경하면 이벤트와 매개변수가 제대로 전달된다.
```html
<div class="box" @mouseover="dealwithEvent($event, 100)">mouseover</div>

dealwithEvent(e,data){
  console.log(e, e.type , data)
}
```
이제 내용을 더 확장해보자.  
``` javascript 
 dealwithEvent(e,data){
  console.log(e, e.type)
    if (data){
      console.log(data)
    } }
```
이제 완성해보자    

```html

 <div class="box" @mouseover="dealwithEvent($event,100)">mouseover</div>
 <div class="box" @mouseleave="dealwithEvent">mouseleave</div>
 <div class="box" @dblclick="dealwithEvent">double click</div>
 <div class="box" @mousemove="mousemove">마우스 위치 : {{x}} ,{{y}}</div> 

// 자바스크립트안에 적으세요. 
dealwithEvent(e,data){
  console.log(e, e.type)
  if (data){
    console.log(data)
  } },
mousemove(e){
  this.x = e.offsetX,
  this.y = e.offsetY
}

```



