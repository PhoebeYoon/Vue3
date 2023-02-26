## html 파일과 js파일을 분리하여 작업과 template 문법

### html, js를 분리해보자
```html
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD" crossorigin="anonymous">
    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>

    <title></title>
</head>
<body>
    <h1>Hello, Vue :)</h1>
    <div id="app">
        <p>{{ title }} - by {{ author }}, {{ pages }}</p>
    </div>
    <script src="./lesson04/app04-1.js"></script>
</body>
</html>

```

```javascript
 Vue.createApp({
       data(){
         return {
         title :'The way back to home',
         author :'Spider man',
         pages : 100
                }
            }
 }).mount('#app');
```
### 템플릿 문법

Vue.js는 렌더링 된 DOM을 기본 Vue 인스턴스의 데이터에 바인딩할 수 있는 html 템플릿 구문을 사용할 수 있는데,여기서 템플릿이란 html, css등의 마크업에 사용된 속성과 vue 인스턴스에서 정의된 데이터를 연결하여 브라우저에서 볼 수 있도록 html로 변환해주는 속성이다.   
우선, 아래의 예제를 보고 자세히 설명하자.  

```html
  <h1>텍스트 보간법과 바인딩</h1>
    <div id="app">
        <p>텍스트 보간법 사용: {{rawHtml}}</p>
        <p>v-html 디렉티브 사용: <span v-html="rawHtml"></span></p>
    </div>
<script>
    Vue.createApp({
        data(){
            return {
                rawHtml : '<span style="color:red"> 내용은빨간색이다</span>',
            }
        }
    }).mount("#app");
</script>
```
결과는 아래 이미지와 같다.   

<img width="351" alt="스크린샷 2023-02-25 오전 11 56 43" src="https://user-images.githubusercontent.com/48478079/221332691-4d0a066d-9833-44c5-abc2-4828bf26d24d.png">

여기서, 이전의 예제에서느느 {{ }} 만 사용해도 해당 내용이 잘 출력되었지만 여기서는 안되는 것처럼 보인다.  
이제 내용을 조금 변경해보자 
```html

<p>텍스트 보간법 사용: {{raw}}</p> # 바뀐 부분 
<p>v-html 디렉티브 사용: <span v-html="rawHtml"></span></p>

return {
        rawHtml : '<span style="color:red"> 내용은빨간색이다</span>',
        raw:'보간법을 이용한 내용' #바뀐부분
            }

```
출력결과는 위의 것과는 다르다.  

<img width="302" alt="스크린샷 2023-02-25 오후 12 00 07" src="https://user-images.githubusercontent.com/48478079/221332839-eef09844-5eef-409f-a74c-833e73aec4c7.png">

이제 단순 변수를 전달할때는 {{}}만 사용해도 작동하지만 태그가 포함된 것을 전달할때는 'v-html'이라는 것을 사용해야 한다는 것을 알수있다.  

정리하자면,  
템플릿 문법은 <b> 보간법과 디렉티브 </b> 있다. 
1) 보간법 (Interpolation) 
    - 문자열 : {{   }} 사용 , mustache(이중 중괄호, 콧수염이라고도 함), 일반텍슽를 해석한다
    - 원시 html : 실제 html를 출력하고자 한다면 'v-html'를 사용한다
    - 속성 : html 속성을 사용하고자 한다면 'v-bind'를 사용한다 (아래 예제를 보자)
    - javascript 표현식: {{ 자바스크립트 표현식 가능 }} 예) {{ numbers +1 }} (아래 예제를 보자)
2) 디렉티브: 디렉티브란: html태그안에 <b>'v-' 로 시작하는 </b>접두사를 사용하는 것으로 단일 자바스크립트 표현식이어야 하며,<b> 요소에 대해 vue가 어떤 일을 하는지를 지정하는 명령어</b>입니다
    - 단일 자바스크립트 표현식에서 v-for는 예외이다
    - 콜론으로 표시되는 '전달인자'를 사용할 수 있다. 예) v-bind:href="url"
    - 동적 전달인자 : 자바스크립트 표현식에 [ ] (대괄호)를 사용하여 arguments를 전달한다 예) v-bind:[속성이름]="url" 
    - 수식어 : 수식어는 (.)점으로 표시되는 특수접미사로 디렉티브를 특별한 방법으로 바인딩한다. 에) 'v-on:submit.prevent:"onSubmit" '


##### html 태그사용
```html

<head>
 <meta charset="UTF-8">
 <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
</head>
<body>
    <h1>Vue Template</h1>
    <div id="app"></div>
<script>
   const app = Vue.createApp({
     template :'<h2> I am Vue template </h2>'
   }).mount('#app');
</script>
</body>
```
크롬 브라우저에서 '개발자도구'를 열어보면, 아래와 같고, <div id="app" data-v-app> 보인다. Vue의 앱이라는 뜻이다.    
    
<img width="330" alt="스크린샷 2023-02-25 오후 12 49 46" src="https://user-images.githubusercontent.com/48478079/221334657-a8b9f7c2-eddd-441b-ae22-46ac8a1a618d.png">

( 여기서 js 코드에 있는 'template' 라는 글자를 변경하면 작동되지 않는다 )
    
template를 사용해서 결과를 얻었다. 하지만 template를 사용하면 수시로 변하는 내용를 반영하기 어렵고 다른 함수를 실행하기도 어렵다. 이제 data()를 대신 사용해보자.   
```html
<h1>Vue Template</h1>
    <div id="app">
     <!-- <p>Template를 사용함</p> -->
            <p>{{title}}</p>
    </div>
<script>
    // js 코드내에 template 이라는 항목을 사용가능하지만 값이 수시로 변하거나 다른 함수를 수행할때는 어렵다. 그래서 data() 함수를 사용해 보자
   const app = Vue.createApp({
        data(){
            return {
            //  object를 리턴한다
                title :'The Result is here'
            }
        }
   }).mount('#app');
</script>
```
   
    
```html
    
    <body>
    <h1>Vue Template</h1>
    <div id="app">
            <p>{{title}} - {{author}} -{{pages}}</p>
    </div>
<script>
Vue.createApp({
        data(){
            return {
                title :'The Load of Rings',
                author :'J. R. R. 톨킨',
                pages : '3권짜리 1볼륨'
            }
        }
   }).mount('#app');
</script>
</body>
```

##### 🌵이번 수업의 마지막으로 아래의 내용과 위의 내용을 비교하여 다른 곳을 찾아보세요
```html
<body>
    <h1>Vue Template</h1>
    <div id="app">
            <p>{{title}} - {{author}} -{{pages}}</p>
    </div>
<script>
const appName = Vue.createApp({
        data(){
            return {
                title :'The Load of Rings',
                author :'J. R. R. 톨킨',
                pages : '3권짜리 1볼륨'
            }
        }
   })
appName.mount('#app')
</script>
</body>
```
