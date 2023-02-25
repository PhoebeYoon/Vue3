## v-text , v-html 사용해 보기

#### 1. v-text
```
<태그 v-text="프로퍼티명"></태그>
텍스트를 있는 그대로 표시해 주는 디렉티브는 v-text 이며 머스태시로 감싸주는 것과 동일하다
```

```html
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Learning Vue</title>
  <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
</head>
<body>
  <div id="app">
    <p v-text="mytext"></p>
    <p v-text="mytext"></p>
    <p v-text="mytext"></p>
  </div>
<script>
new Vue({
    el:'#app',
    data:{
        mytext:"Hello, Vue~"
    }
})
</script>
</body>
</html>

```

#### 2. v-html
```
<태그 v-html="프로퍼티명"></태그>
html로 표시하고자 할때 사용한다
```
```html
<body>
  <h2>HTML로 표시하는 예제</h2>
	<div id="app">
		<p>{{ myText }}</p>
		<p v-text="myText"></p>
		<p v-html="myText"></p>
	</div>
<script>
	new Vue({
	el: '#app',
	data: {
	myText:'<h1>Hello!!!</h1>'
	}
	})
</script>
</body>
```

