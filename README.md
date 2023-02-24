# Vue3 Lesson 를 위해 


파일이름 : index.html   
```html

<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script
    <title>Learning Vue</title>
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

