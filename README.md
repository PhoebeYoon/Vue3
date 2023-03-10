:cactus: Vue3 Lesson 

## v-on 디렉티브 : 이벤트와 연결

```
<p v-on:이벤트="메소드이름"> </p>
메소드는 인스턴스안에 methods 옵션을 통해 추가하면 됩니다 
```
### v-on:이벤트명 과 @이벤트명은 동일하다
```
<a v-on:click="do">
<a @click="do"> (v-on은 생략할 수 있고 v-on 대신 @ 을 사용합니다 )
```

```html
<h2> v-on 디렉티브</h2>
<div id="app">
  <p>{{ count }}</p>
  <button v-on:click="increase">Increase</button>
</div>
<script>
Vue.createApp({
data(){ 
      return { count:1} 
  },
methods:{
  increase:function(){
    //  console.log('test')
    this.count++ // count앞에 this를 붙여줘야 합니다
   } }
}).mount('#app')
</script>
```
methods에서 data 에 선언된 변수를 가져와 사용하려면 this 키워드를 붙여줘야 합니다


### 다른 함수를 부름
```html
<h2> v-on 디렉티브</h2>
<div id="app">
  <button  :disabled="false"  v-on:click="btn"> LIKE </button>
</div>
<script>
function myF(){
  alert("myF 함수 실행");
}
Vue.createApp({
data(){ 
      return { } 
  },
methods:{
  btn:function(){
    //console.log('버튼작동확인')
    myF();
  }
}
}).mount('#app')
</script>

```

### 한번 클릭하고 두번은 클릭할 수 없게 하는 예제
```html
<h2> v-on 디렉티브</h2>
<div id="app">
  <button value="good" v-bind:disabled="isClick" @click="btn">LIKE</button>
</div>
<script>
function myF(){
  alert("Liked");
}
Vue.createApp({
data(){ 
      return { isClick : false} 
  },
methods:{
  btn:function(){
     this.isClick=true;
     myF()
  }
}
}).mount('#app')
</script>

```
### 파라미터(parameter)를 전달하는 메소드

```
<button v-on:click="메소드(파라미터)">

인스턴스안에서,
methods:{
  메소드명:function(파라미터) {
  }
}
```
아래의 예제에서 실행되는 메소드는 countUp 뿐이다. 그러므로 1씩, 3씩, 10씩 증가하기 위해서는 증가하는 값를 파라미터로 전달해야 한다.  
```html
<h2> v-on 디렉티브</h2>
<div id="app">
 <p>{{ count }}</p>
 <button v-on:click="countUp(1)">1씩증가</button>
 <button @click="countUp(3)">3씩증가</button>
 <button v-on:click="countUp(10)">10씩증가</button>
</div>
<script>

Vue.createApp({
data(){ 
      return { count:0} 
  },
methods:{
  countUp:function(value){
    this.count +=value;
  }
}
}).mount('#app')
</script>

```   

마우스를 움직여 좌표를 얻는 예제를 만들어보자.   

``` html
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <script src="https://unpkg.com/vue@next"></script>
</head>
<body>
  <div id="app">
    <div class="box" v-on:mousemove="getCoord">
        Hover me
    </div>
    <p>x: {{ x }}</p>
    <p>y: {{ y }}</p>
</div>
<script>
Vue.createApp({
  data(){
    return {
      name:'Francis',
      x:0,
      y:0
    }
    },
methods:{
  getCoord(event){
    this.x = event.clientX;
    this.y = event.clientY;
  }
}
}).mount("#app")
</script>
<style>
.box {
  background: red;
  width:200px; height:200px;
  color:#fff; text-align: center;
}
</style>
</body>
</html>
```



