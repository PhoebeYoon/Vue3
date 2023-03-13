##### 🌵 Vue3.js

## 컴포넌트에 대해 알아보겠습니다.  

나중에 part2에서도 다시 언급할것이지만 컴포넌트에 대해 간단히 알아보겠습니다.   
컴포넌트는 Vue의 가장 강력한 기능 중 하나로써 기본 HTML 엘리먼트를 확장하여 재사용 가능한 코드입니다. 이 컴포넌트는 Vue의 컴파일러에 의해 동작이 추가된 사용자 지정 엘리먼트으로 우리가 앞의 수업에서 사용했던 data(),  methods, computed, watch등 속성을 사용할 수 있습니다.
또한 Vue 컴포넌트는 Vue 인스턴스이기도 합니다.  

생성하는 방법은, Vue.component(tagName, options)입니다
```
Vue.component('my-component', {
  // 옵션
})
```  
우리가 늘 사용하던 Vue 인스턴스생성에 시간을 좀 지연시켜서 만들어 보겠습니다. 
```html
<body>
  <div id="app"> {{ name}} </div>
  <script>
  const App = {
    data(){
      return {
        name :'Kim'
      }
    }
  }
  setTimeout(()=>{
    Vue.createApp(App).mount('#app')
  },3000)
  </script>
</body>
```
5초후에 인스턴스가 웹페이지에 mount되는것을 확인할 수 있습니다. 이제 템플릿을 넣어보겠습니다. 이 템플릿은 html태그가 될 예정입니다

```html
<body>
  <div id="app"></div>
  <script>
  const App = {
    data(){
      return {
        name :'Kim'
      }
    },
    template:` <div> Welcome ${name} </div>`
  }
  setTimeout(()=>{
    Vue.createApp(App).mount('#app')
  },3000)
  </script>
```   
실행하면 처음에는 아무것도 보이지 않다가 3초후에 'Welcome' 이라는 글자가 나타납니다.   

이제 인스턴스안에 살아있는(?) 컴포넌트를 만들어보겠습니다.  

``` html
<body>
  <div id="app"> 
    <user-name>{{name}}</user-name>
  </div>
  <script>
  const app = Vue.createApp({ })  
  app.component('user-name',{
    data(){
      return {
        name :'Kim'
      }
    },
    template:` <div> Welcome ${name} </div>`
  } )
 app.mount('#app')
  </script>
</body>

```
실행후 브라우저의 개발자도구를 확인해 보시기 바랍니다. 
