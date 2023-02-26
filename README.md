:cactus: Vue3 Lesson 
## v-for 디렉티브에 대해 알아봅시다.  

```
문법 : 
<p v-for="변수 in [배열]"> 반복할 내용 </p>
<p v-for="변수 in 최대값"> 반복할 내용 </p>
<p v-for="(변수, 인덱스) in [배열]"> 반복할 내용 </p>
여기서 예로 <p> 사용
```
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
