# 정리

## Vue 인스턴스 만들기

```
new Vue({ vue인스턴스 내용}
또는 
var 변수명 = new Vue({ vue 인스턴스 내용})
```
vue 인스턴스에는 "el옵션' 과 "data옵션" 이 있다.
html내용중 ```<태그 id="아이디명">``` 과 el옵션의 ```el:"#아이디명" ```으로 지정된다.  
data옵션은 ``` data: { 데이터 내용}  ``` 으로

```
<div id="id명"> </div>
new Vue(
{
  el:"#id명",
  data: { 프로퍼티이름: 프로퍼티값,
          프로퍼티이름: 프로퍼티값 }
})

```

Vue 인스턴스에는 다음과 같은 내용이 나옵니다. 한꺼번에 모두 사용해야 하는 것은 아니며 필요에 따라 사용합니다.
```vue
new Vue({
         el : 어느 html요소를 연결할 것인가
       data : 어떤 데이터인가
    methods : 어떤 처리를 할것인가
   computed : 어느 데이터를 사용해서 계산할것인가
      watch : 어느 데이터를 감시할 것인가
})

```

또한, 아래의 data(){ } 와 data:()=>{ } 는 모두 사용가능하다. 

```
//ES5 문법
data () {
 return { 데이터를 넣어주세요 }
 }

//ES6 문법
data:() => ({ 데이터를 넣어주세요 })
```

```html
  <h1>Hello, Vue :)</h1>
  <div id="app">
    {{ count}}
  </div>
<script>
new Vue({
    el: "#app",
	data: {
		count:0
	}
   })
</script>
```

