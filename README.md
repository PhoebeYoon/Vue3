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


1) 템플릿에서 사용되는 vue의 속성과 문법
- 데이터 바인딩 : html 요소를 vue 인스턴스의 데이터와 연결하는 것을 의미. 
- {{   }} 사용 : vue 인스턴스의 데이터를 html 태그로 연결하는 가장 기본적인 텍스트 삽입방식으로 mustache(이중 중괄호, 콧수염이라고도 함) 문법을 사용한 텍스트 보간법.
- 'v-bind' : 아이디, 클래스등의 html속성값에 vue의 인스턴스 데이터를 연결할때 사용되는 명령어
2) 템플릿 사용방법 : html태그안에 'v-' 로 시작.


