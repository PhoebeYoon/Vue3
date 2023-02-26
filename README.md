## v-bind 디렉티브와 스타일 

```
<a v-bind:href="url">
<a :href="url">
```
### 인라인 방식으로 속성지정하기 (href, src, text-align, color, font-size, background-color)
블록태그에 :align="left (center, right)"


```html
<div id="app">
	<p><a v-bind:href="naver_link">네이버로 연결</a></p>
	<p><img :src="face2_name">face2.png 표시</img></p>
	<p :align="align_left">텍스트를 왼쪽 정렬</p>
	<p :align="align_right">텍스트를 오른쪽 정렬</p>
	<p :align="align_center">텍스트를 가운데 정렬</p>
	<p v-bind:style="{ color: inline_font_red }">인라인 스타일로 글자색을 빨간색으로</p>
	<p v-bind:style="{ color: inline_font_red, fontSize : inline_size_150 }">인라인 스타일로 글자크기를 150% 크게 빨간색으로</p>
	<p :style="{ color: inline_font_red, fontSize : inline_size_150, backgroundColor : inline_background}">
		인라인 스타일로 글자크기를 150% 크게 빨간색으로 배경은 노란색으로</p>
	<p :class="blue_underline_class">blue-underline class 지정</p>
	<p :class="[blue_underline_class, dark_class]">blue-underline, dark class 지정</p>
</div>
<script>
	new Vue({
		el: '#app',
		data: {
			naver_link : 'https://naver.com',
			face2_name : 'face2.png',
			align_right : 'right',
			align_left : 'left',
			align_center : 'center',
			inline_font_red : 'red',
			inline_size_150 : '150%',
			inline_background : 'yellow',
			blue_underline_class : 'blue-underline',
			strike_through_class : 'strike-through',
			dark_class : 'dark',
		}
	})
</script>
</body>

```
### 클래스로 속성지정하기 
```html
<h2>클래스 지정 예제</h2>
<style>
    .strike-through {
        text-decoration: line-through;
        color:#111 }
    .dark { background-color:magenta;}
</style>
<div id="app">			
    <p class="strike-through">직접 클래스 지정</p>
    <p v-bind:class="myClass">v-bind로 클래스 지정</p>
    <p v-bind:class="[myClass, darkClass]">v-bind로 복수의 클래스 지정/p>
    <p v-bind:class="{'strike-through': isON}">데이터로 클래스 ON/OFF</p>
</div>

<script>
    new Vue({
        el: '#app',
        data: {
            myClass: 'strike-through',
            darkClass: 'dark',
            isON: true
        }
    })
</script>
</body>
```

'strike-through': isON 에서 inON이 true / false 를 적용한 뒤 변경내용을 확인해보자.  
Vue에서 사용하는 방법이니 잘 익혀둡시다

