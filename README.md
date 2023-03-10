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
