## v-bind 디렉티브와 스타일 

```
<a v-bind:href="url">
<a :href="url">
```
### href, src, text-align, color, font-size, background-color,
```html
<div id="app">
    <img src="./img/face1.png" >
    <img v-bind:src="fileName">
    <br><br>
    <a href="https://www.naver.com">직접 네이버가기</a> 
    <a v-bind:href="urllink1">v-bind로 지정</a>
    <a :href="urllink1">v-bind 숏으로 지정</a>
    <br> <br>
    <p style="text-align:right">오른쪽정렬</p>
    <p v-bind:style="txtAlign">오른쪽정렬</p>
    <p style="color:red">글자</p>
    <p v-bind:style="txtColor">글자</p>

    <p style="font-size:20px">글자크기</p>
    <p v-bind:style="font1">글자크기</p>
    <p :style="font2">글자크기</p>

    <p style="background-color: deeppink;">배경색상</p>
    <p v-bind:style="bg1">배경색상</p>
    <p :style="bg2">배경색상</p>
    
</div>
<script>
    new Vue({
        el:'#app',
        data :{
            fileName:'./img/face2.png',
            urllink1 :'https://www.naver.com',
            txtAlign: 'textAlign:right',
            txtColor: 'color:blue',
            font1 : 'fontSize  : 150%',
            font2 : 'fontSize  : 150%',
            bg1:'backgroundColor: deepskyblue',
            bg2:'backgroundColor: orange'
        }
        });
</script>
</body>

```

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

'strike-through': isON 에서 inON이 true / false 를 적용한 뒤 변경내용을 확인해보자
Vue에서 사용하는 방법이니 잘 익혀둡시다

