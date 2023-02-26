:cactus: Vue3 Lesson 
## v-if 디렉티브에 , v-show 대해 알아보자. 
조건에 따라 내용을 표시하거나 표시하지 않거나 합니다.

```
<p v-if="조건"> 조건이 ture 일때 표시하는 내용 </p>
<p v-else > 조건이 false 일때 표시하는 내용 </p>
```

```
<p v-if="조건1"> 조건1이 ture 일때 표시하는 내용 </p>
<p v-else-if="조건2"> 조건1이 false 이고, 조건2가 ture 일때 표시하는 내용 </p>
<p v-else > 우의 2개의 조건이 false일대 표시하는 내용 </p>
```

### 1. v-if, v-if v-else, v-if v-else-if, v-else 
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>v-if 디렉티브</title>
  <script src="https://unpkg.com/vue@3.0.0"></script>
</head>
<body>
<div id="app">
  <div v-if="true">Vue is awesome-true!</div>
  <div v-if="false">Vue is awesome-false!</div>
  <hr>
  <div v-if="false">Vue is wonderful!-true</div>
  <div v-else>Vue is wonderful - false</div>
  <hr>
  <div v-if="false">v-if</div>
  <div v-else-if="true">v-else-if</div>
  <div v-else>v-else</div>
</div>
<script>
Vue.createApp({
data() { return { } } }).mount('#app')
</script>
</body>
</html>
```

#### 2. v-if 사용 예
```html
<div id="app">
  <p v-if="isShow">Vue is beautiful - 1 </p>
  <p v-else="isShow">Vue is beautiful - 2</p>
</div>
<script>
Vue.createApp({
data() { return { 
  isShow:false
} } }).mount('#app')
</script>

```

```html
<div id="app">
  <p v-if="type=='A'">A</p>
  <p v-else-if="type=='B'">B</p>
  <p v-else>C</p>
</div>
<script>
Vue.createApp({
data() { return { 
  // type:'A'
  //  type:'B'
  type:'Z'
} } }).mount('#app')
</script>

```
#### 3. v-show 사용 예


```html
<div id="app">
  <p v-show="isShown==true">A</p>
</div>
<script>
Vue.createApp({
data() { return { 
  isShown :true
} } }).mount('#app')
</script>
```
- 위의 코드에서 isShown ==true 일때 결과  
<img width="260" alt="스크린샷 2023-02-26 오후 4 48 21" src="https://user-images.githubusercontent.com/48478079/221398652-9605ce93-d621-4657-9cd4-6dbeda0629f2.png">   
- 위의 코드에서 isShown ==false 일때 결과   
<img width="360" alt="스크린샷 2023-02-26 오후 4 49 41" src="https://user-images.githubusercontent.com/48478079/221398731-f38efb4c-c51b-49fc-88ce-bd10a55218c3.png">



