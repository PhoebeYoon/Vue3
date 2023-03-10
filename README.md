
## vue에서 이벤트핸들링할때 함수에 넘겨줄 인자가 없을때
``` html
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <meta http-equiv="X-UA-Compatible" content="ie=edge">
   <script src="https://unpkg.com/vue@next"></script>
   <title>Document</title>
</head>
<body>
<div id="app">
  <input type="text" @change="onChangeInput"> 
</div>
</body>
<script>
Vue.createApp({
  data(){
    return {
       message:''
    }
  },
  methods:{
    onChangeInput(event) {
    this.message = event.target.value
    console.log(this.message)
  }
 }
}).mount("#app")
</script>
</html>
```  
위 예제에서는 @change="onChangeInput" 에서 인자를 넘기지 않지만 methods에서는 onChangeInput(event)로 받는다. 그리고 그것을 (event.target.value)이용해서 콘솔창에 입력박스에서 입력한 내용을 출력한다. 디폴트이다.
그런데 만약 특정한 매개변수를 넘겨주고 싶다면 어떻게 할까?   
이때 사용하는 것이 $event 이다.


## event 객체와 매개변수를 같이 사용할때
```html
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <meta http-equiv="X-UA-Compatible" content="ie=edge">
   <script src="https://unpkg.com/vue@next"></script>
   <title>Document</title>
</head>
<body>
<div id="app">
  <button @click="handler('click 1 = hi', $event)">Click me</button>
  <button @click="handler('click 2 = hello', $event)">Click me</button>
</div>
</body>
<script>
Vue.createApp({
  data(){
    return {
    }
  },
  methods:{
    handler(msg, event) {
      console.log(msg)
      console.log(event)
    }
 }
}).mount("#app")
</script>
</html>

```
다른 예제로는,  
``` html
<div id="app">
  <input type="text" @change="onChangeInput('hello', $event)"> 
</div>

<script>
Vue.createApp({
  data(){
    return {
       message:''
    }
  },
  methods:{
    onChangeInput(i, e) {
    this.message = i
    console.log(this.message)
    console.log(e.target.value)
  }
 }
}).mount("#app")
</script>
```



## v-model를 form에서 사용할때




```html
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <meta http-equiv="X-UA-Compatible" content="ie=edge">
   <script src="https://unpkg.com/vue@next"></script>

   <title>Document</title>
</head>
<body>
<div id="app">
  <!-- <h1>{{ name }}</h1>
  <button v-on:click.right="changeName('Ron', $event)">
      Change name
  </button> -->
  <form v-on:submit.prevent="handleForm">
    <input/>
    <button type="submit">
        Submit
    </button> 
  </form>
</div>
</body>
<script>
const App = {
  data(){
    return {
        name:'Francis'
    }
  },
  methods:{
    handleForm(){
    console.log('Submit form')
},
changeName(newName, event){
    this.name = newName;
    console.log(event)
    } 
}}
Vue.createApp(App).mount('#app')
</script>
</html>

```    
예제에서 폼태그에서 submit를 하면 페이지를 리로드하면서 기존내용이 사라지는것을 방지하기 위해 v-on:submit.prevent를 사용했다.   
또한 changeName('Ron', $event)에서 이벤트를 전송하고자 $event를 사용했다. 
