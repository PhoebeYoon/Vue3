:cactus: Vue3 Lesson 

## v-model(입력폼과 데이터연결)

폼입력과 데이터를 연결하기 위해 v-model디렉티브를 사용한다. Vue 인스턴스의 데이터가 웹페이지에 표시되고 웹페이지에서 입력한 값이 Vue인스턴스의 데이너에 반영되므로 양방향 바인딩이라고 해야 한다.

```
<태그명 v-model="프로퍼티명">
```
### input 사용예
```html
<div id="app">
  <input v-model="myName" placeholder="이름" type="text">
  <p>나는 {{ myName }} 입니다</p> 
</div>
<script>
Vue.createApp({
data(){
  return { myName:''}
}
}).mount("#app")
</script>

```
### textarea 사용예
``` html
<div id="app">
 <textarea v-model="myText" id="" cols="30" rows="10"></textarea>
 <p>문장은 {{ myText }}이고, </p>
 <p>글자수는 {{ myText.length }} 자입니다 </p>
</div>
<script>
Vue.createApp({
data(){
  return { myText:'Have a good day!'}
}
}).mount("#app")
</script>

```

### input type=checkobx 사용예
```html
<div id="app">
<input type="checkbox" v-model="checking">
현재상태는 {{ checking }}
</div>
<script>
Vue.createApp({
data(){
  return { checking: true}
}
}).mount("#app")
</script>

```
<img width="120" alt="스크린샷 2023-02-26 오후 9 42 43" src="https://user-images.githubusercontent.com/48478079/221411146-8458916a-539a-462f-a1f3-313c2b09ff86.png">

<img width="120" alt="스크린샷 2023-02-26 오후 9 42 52" src="https://user-images.githubusercontent.com/48478079/221411151-0be7b82b-a572-411d-a37e-2090a63cb556.png">




### checkbox의 값을 인스턴스의 테이터와 연결  
```html
<div id="app">
  <input type="checkbox" value="red"   v-model="checking">
  <input type="checkbox" value="green" v-model="checking">
  <input type="checkbox" value="blue"  v-model="checking">
  <div> 당신이 선택한 색상은 {{ checking }}</div>
</div>
<script>
Vue.createApp({
data(){
  return { checking :[ ]}
}
}).mount("#app")
</script>

```  
<img width="263" alt="스크린샷 2023-02-26 오후 9 50 36" src="https://user-images.githubusercontent.com/48478079/221411523-d5b78acd-823d-4d5b-9a08-bf468d3c7389.png">

### 동의에 체크하면 버튼이 활성화되는 예
``` html
<div id="app">
  <label>
    <input type="checkbox" v-model="myAgree" >
    동의합니다.</label>
    <button v-bind:disabled="myAgree==false">동의하고 제출하기 </button>
</div>
<script>
Vue.createApp({
data(){
  return { 	myAgree: false}
}
}).mount("#app")
</script>

```


