## Vue3 Lesson 를 위해 무작정 한번 만들어보자

### :cactus:  CDN vs NPM 
vue로 만든 파일을 실행하려면 여러가지 환경설정을 해야 합니다. CDN 방식은 이런 환경설정을 링크를 통해서 해결하는 것입니다. 처음에 vue을 배울때 좋죠.     
<b> CDN은 Content Delivery Network</b>의 약자이니 영어로 보시면 확실히 이해가 될 것입니다.   
그래서 script 태그에 해당 링크를 넣어주는 것입니다. 마치 제이쿼리할때처럼요.  
그리고 <b>NPM은 Node Package Manager</b> 의 약자로 한마디로 패키지를 당신의 컴에 설치하겠다는 뜻입니다.  
즉 vue가 실행될 수 있는 환경을 당신의 컴에 만들겠다는 의미죠.  
그래서 vue가 실행될때 필요한 node.js가 있는지 확인하는 것입니다.

이제 무조건 하나 만들어 봅시다.  :file_folder:Basics :file_folder: index.html   
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

