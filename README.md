## Using the Global Build
#### 여기에서는 Vue가 사용하는 몇개의 API를 살펴보는 것이 목적이다
```html
 <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>

<div id="myApp">{{ msg }}</div>

<script>
  const { createApp } = Vue

  createApp({
    data() {
     return {
            msg: '안녕하세요 Vue의 세계에 오셨습니다'
          }
  }).mount('#myApp')
</script>

```
### API Reference 
https://vuejs.org/api/ 사이트에 가서 Vue에서 사용하는 api를 몇개만 확인해 보자.  



#### 1. createApp()
어플리케이션 인스턴스를 생성한다. API 중 하나다.
> Application API
createApp() - 첫번째 인수는 루트 컴포넌트이다. 두번째 인수는 선택적으로 사용할 수 있고 루트 컴포넌트에 전달할 속성이다
``` Type : function createApp(rootComponent: Component, rootProps?: object): App ```
##### 인라인 루트 컴포넌트 : 
```javascript
import { createApp } from 'vue'

const app = createApp({
  /* root component options */
})
```
##### imported 한 컴포넌트 
``` javascript
import { createApp } from 'vue'
import App from './App.vue'

const app = createApp(App)
```
위의 내용을 복사 붙여넣기해도 실행되지 않는다 왜냐하면 이것에 사용되는 파일을 만들지 않았기 때문이다. 여기에서는 createApp() api 가 루트 컴포넌트라는 것을 기억하자. 루트 컴포넌트는 어플리케이션 실행시 첫번째로 실행되어지는 것정도로 이해하자.   

#### 2. app.mount()
``` javascript
interface App {
  mount(rootContainer: Element | string): ComponentPublicInstance
}

```
여기서의 인수는 DOM엘리먼트 또는 CSS선택자일 것으로 루트 컴포넌트의 인스턴스를 리턴한다. 각 인스턴스에서 mount()는 한번만 불려진다.   
``` javascript
import { createApp } from 'vue'
const app = createApp(/* ... */)

app.mount('#app')
```
```javascript
app.mount(document.body.firstChild)

```

### Options: State 
https://vuejs.org/api/options-state.html 클릭

#### 1. data() 
이것은 컴포넌트 인스턴스의 초기 반응상태를 반환하는 함수이다. 이 함수는 일반 자바스크립트 객체를 반환하며 Vue에 의해 반응적으로 만들어진다. 인스턴스가 생성되면 반응형데이터 객체를 액세스할 수 있게 한다. 
