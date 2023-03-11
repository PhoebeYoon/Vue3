##### 🌵 Vue3.js

## v-text 
``` html
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <meta http-equiv="X-UA-Compatible" content="ie=edge">
   <script src="https://unpkg.com/vue@next"></script>
</head>
<body>
<div id="app">
    <div v-text="blue">
        This is my content
    </div>
    <div> {{ msg }} </div>
</div>
</body>
<script>
Vue.createApp({
  data(){
    return {
      blue :'Learning Vue is fun',
      msg : 'Write less Do more '
       }
    }   
}).mount("#app")
</script>
<style>

</style>
</html>
```

``` html
<div id="app">
  <h1>Hello {{ userName }}!</h1>
  <h1 v-text="userName"></h1>
  <p>이름 : {{ user.name}}</p>
  <p v-text="user.age">나이는 안 보여요</p>
</div>
</body>
<script>
Vue.createApp({
  data(){
    return {
      userName:'Mr.Kim',
      user:{
        name:'Mr. Park',
        age :20
      }
       }
    }   
}).mount("#app")
</script>
```



