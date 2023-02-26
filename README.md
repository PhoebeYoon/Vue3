:cactus: Vue3 Lesson 

## v-model(입력폼과 데이터연결)

폼입력과 데이터를 연결하기 위해 v-model디렉티브를 사용한다. Vue 인스턴스의 데이터가 웹페이지에 표시되고 웹페이지에서 입력한 값이 Vue인스턴스의 데이너에 반영되므로 양방향 바인딩이라고 해야 한다.

```
<태그명 v-model="프로퍼티명">
```

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
