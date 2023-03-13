##### 🌵 Vue3.js

## 인스턴스를 생성하는 문장에 따라 이런 차이가 있습니다. 

```html
  <div id="app1"> application 1 : {{ value}}
    <button @click="changeValue">change value</button>
  </div>
  <div id="app2"> application 2 : {{ value }}</div>
   <script>
    const App1 = {
      data(){
        return { value :'Instance one working'}
      },
      methods:{ changeValue(){
      App2.value='The value changed'
      }}
    }
    Vue.createApp(App1).mount("#app1")
    
    const App2 = {
      data(){
        return { value :'Instance two working'}
      }
    }

    Vue.createApp(App2).mount("#app2")
  
  </script>
```   
위의 내용은 인스턴스가 모두 생성되어서 value의 값을 제대로 출력합니다. 그런데 여기서 App1에 버튼을 만들어서 App2 인스턴스의 value을 바꾸려고 합니다.  
버튼을 클릭하지만 App2의 value는 바뀌질 않습니다.   
이제 아래의 방법으로 인스턴스를 생성해 보겠습니다.  

```javascript
<script>
    const App1 = Vue.createApp({
      data(){
        return { value: 'Instance one working'}
      },
      methods:{
        changeValue(){
          App2.value='The value changed'
        }
      }
    }).mount('#app1')

    const App2 = Vue.createApp({
      data(){
        return { value:'Instance two working' }
      }
    }).mount('#app2')
  </script>

```   
언뜻보면 차이가 없는것처럼 보입니다.  이제 버튼을 클릭해보십시요. 태그는 바뀐것이 없지만 App2의 value값이 변경됩니다.   
첫번째 예제에서는 인스턴스가 ```   Vue.createApp(App1).mount("#app1") ``` 에서 생성되기 때문입니다. 첫번째 예제의 ```const App1 = { data } ```는 그냥 객체라고 보시면 됩니다.
