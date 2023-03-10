##### 🌵 Vue3.js


``` html
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <script src="https://unpkg.com/vue@next"></script>
</head>
<body>
  <div id="app">
    <p>{{ name }}</p>
    <p>{{ name }}</p>
    <p>{{ update() }}</p>
  </div>
  <script>
    Vue.createApp({
      data(){
        return {
          name :'Smith'
        }
      },
      methods: {
        update(){
          setTimeout( ()=>{
            this.name ='John'
          }, 2000)
        }
      }
    }).mount("#app")
  </script>
</body>
</html>
```    
에서 2초가 지나면 Smith 에서 John으로 모두 바뀐다.  여기에 v-once를 사용해보자  
``` <p v-once>{{ name }}</p> ``` 이렇게 변경하면 Smithe, John 으로 결과가 나온다

