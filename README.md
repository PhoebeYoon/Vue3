:cactus: Vue3 Lesson 
## v-for 디렉티브에 대해 알아봅시다.  

```
문법 : 
<p v-for="변수 in [배열]"> 반복할 내용 </p>
<p v-for="변수 in 최대값"> 반복할 내용 </p>
<p v-for="(변수, 인덱스) in [배열]"> 반복할 내용 </p>
여기서 예로 <p> 사용
```
### 1. 변수 in [배열]
```html
<html>
	<head>
		<meta charset="UTF-8">
		<title>Vue.js sample</title>
		<script src="https://unpkg.com/vue@3.0.0"></script>
	</head>
	
	<body>
		<h2>배열 데이터를 리스트로 표시하는 예제 </h2>
		<div id="app">
			<ul> <li v-for="item in myArray">{{ item }}</li></ul>
		</div>
		<script>
		Vue.createApp({
			data() {
				return {
					myArray:['🍎','🍉','🥝','🍑']
				}
			}
		}).mount('#app')
		</script>
	</body>
</html>

```
### 2. 변수 in 오브젝트 
```html
!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<title>Vue.js sample</title>
	<script src="https://unpkg.com/vue@3.0.0"></script>
	</head>
	
	<body>
        <h2>오브젝트 배열 데이터를 리스트로 표시하는 예제 </h2>
	<div id="app">
	<ul> 
             <li v-for="item in objArray">{{ item }}</li>
             <li v-for="item in objArray">{{ item.name }} - {{item.price}} 원</li>
        </ul>
	</div>
<script>
   Vue.createApp({
	data() {
	return {
	objArray: [
		{name: '쨈빵', price: 1000},
		{name: '멜론빵', price: 1200},
		{name: '크로와사', price: 1500}
		]
	}
}
}).mount('#app')
</script>
</body>
</html>

```
#### 3. 변수 in 최대값 
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Vue.js sample</title>
  <script src="https://unpkg.com/vue@3.0.0"></script>
</head>

<body>
  <h2>구구단 5단 예제 </h2>
  <div id="app">
  <ul> 
      <li v-for="n in 10"> 5 x {{n}} ={{ 5 * n}}</li>
  </ul>
  </div>
  <script>
  Vue.createApp({
    data() {
      return {
      }
    }
  }).mount('#app')
  </script>
</body>
</html>

```

#### 3. 인덱스, 아이템 in [배열] 
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Vue.js sample</title>
  <script src="https://unpkg.com/vue@3.0.0"></script>
</head>
<body>
  <h2>인덱스와 오브젝트  </h2>
  <div id="app">
  <ul> 
    <li v-for="(item, index ) in myArray">{{ index }} : {{ item }}</li>
  </ul>
  </div>
  <script>
  Vue.createApp({
    data() {
      return {
        myArray: ['크림빵','팥빵','크로와상','슈크림빵']
      }
    }
  }).mount('#app')
  </script>
</body>
</html>

```
