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
		{name: '팥빵', price: 1000},
		{name: '멜론빵', price: 1200},
		{name: '크로와', price: 1500}
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


#### 테이블로 표시하는 예제 
```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Vue.js sample</title>
  <script src="https://unpkg.com/vue@3.0.0"></script>
<style>
  table { width: 100%; text-align: left;}
  table th { padding: 12px;
    border-bottom: 2px solid darkgray }
  table td { padding: 12px;}
  table tr:nth-of-type(even) { background-color: rgba(0, 0, 255, 0.1); }
</style>
</head>
<body>
<h2>배열 데이터를 테이블로 표시하는 예제</h2>
<div id="app">
<h3>관심 받고 있는 언어 랭킹</h3>
<table>
<thead>
<!-- 테이블 헤어 반복 -->
<th v-for="item in header">{{ item }}</th>
</thead>
<tbody>
  <!-- 1행 반복 -->
  <tr v-for="line in ranking">
    <!-- 1데이터 반복 -->
    <td v-for="item in line">{{ item }}</td>
  </tr>
</tbody>
</table>
</div>

<script>
Vue.createApp({
data() {
return {
  header : [ "프로그램언어",2018,2013,2008,2003,1998],
  ranking: [
      ['Java',1,2,1,1,16],
      ['C',2,1,2,2,1],
      ['C++',3,4,3,3,2],
      ['Python',4,7,6,11,23],
      ['JavaScript',7,10,8,7,20]
    ]
}
}
}).mount('#app')
</script>
</body>
</html>

```
