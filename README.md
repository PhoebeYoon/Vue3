## Vue3 Lesson 를 위해 무작정 한번 만들어보자


파일이름 : index.html   
```html

<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>   
    <title></title>
</head>
<body>
    <div id="app">
        {{ message }}
    </div>
    <script src="app.js"></script>
</body>
</html>
```


파일이름 : app.js   
```javascript
var app = new Vue(
    {
        el:'#app',
        data:{
            message:'안녕하세요 Vue 입니다'
        }
    }
)

```
결과는,  ( live server를 실행시킨 상태이다)  
<img width="304" alt="스크린샷 2023-02-24 오후 2 57 36" src="https://user-images.githubusercontent.com/48478079/221103454-26199283-443e-4ba7-8b8f-ed9c538dcee7.png">

코드를 살펴보자.   
<img width="790" alt="스크린샷 2023-02-24 오후 3 00 33" src="https://user-images.githubusercontent.com/48478079/221104253-df3c24fa-9244-42ab-8cc5-14a9f78564cf.png">

이제 코드를 조금 바꿔서 사용해보자.   
index.html 로 저장   
```html
<body>
    <div id="demo">
        {{ message }}
    </div>
    <script src="app1.js"></script>
</body>

```

아래의 코드는 app1.js로 저장한다
```javascript
var app = new Vue(
    {
        el:'#demo',
        data:{
            message:'id=demo 로'
        }
    }
)
```

다시 살펴보자.

<img width="791" alt="스크린샷 2023-02-24 오후 3 20 09" src="https://user-images.githubusercontent.com/48478079/221107207-1909fe49-089e-4423-bc6c-f6823dbd5305.png">

