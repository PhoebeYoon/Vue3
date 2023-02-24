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
