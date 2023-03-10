
## 여기에서는 Vue가 사용하는 몇개의 API를 살펴보는 것이 목적입니다. 
이전 학습에서 했던 내용과 조금 다릅니다. 이것에 대해서는 다른 브랜치에서 따로 설명을 넣었습니다

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
createApp() - 첫번째 인수는 루트 컴포넌트이다. 두번째 인수는 선택적으로 사용할 수 있고 루트 컴포넌트에 전달할 속성입니다.   
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
위의 것들을 보면 비슷한 듯 하면서도 조금씩 다릅니다. 왜냐하면 버전에 따라 조금씩 달라졌기 때문입니다. 여기서는 createApp 이라는 것을 이해하는 것이 목적이니 일단  이렇게도 사용했구나 하고 이해하십시요. 
그래서 여기에서는 createApp() api 가 루트 컴포넌트라는 것을 기억하시면 됩니다. 루트 컴포넌트는 어플리케이션 실행시 첫번째로 실행되어지는 것이다 정도로 이해하시면 됩니다.   

#### 2. app.mount()
``` javascript
interface App {
  mount(rootContainer: Element | string): ComponentPublicInstance
}
```
여기서의 인수는 DOM엘리먼트 또는 CSS선택자일 것으로 루트 컴포넌트의 인스턴스를 리턴한다. 뭔가 복잡해 보이는데 이것은 문법이 이렇게 되어 있다는 것이지 실제 사용하는 예를 보면 이렇게 복잡하지 않습니다.      
``` javascript
import { createApp } from 'vue'
const app = createApp(/* ... */)

app.mount('#app')
```
```javascript
app.mount(document.body.firstChild)
```
 mount()에는 DOM엘리먼트 또는 CSS선택자를 넣는데, 여러분은 '#app'를 많이 보셨을 것입니다. 이것은 유일하게 구별하는 선택자가 '아이디'이고 우리가 웹어플리케이션을 만드니까 'app' 이라는 이름을 흔히 사용하는것입니다. 동사무소에서 비치해 놓은 문서양식의 샘플에 모든 신청자 이름은 '홍길동'으로 되어 있지요. 우리는 홍길동을 보면 아 내 이름을 여기에 적는거구나 하잖아요. 뭐 그런식이죠.  
그리고 document.body.firstChild 라고 되어 있는 부분에서 vue2에서는 루트엘리먼트는 반드시 1개여야 했지만 vue3에서는 그렇지 않아요. 하지만 우리는 호환성을 위해 일단 1개로 사용하도록 합니다.  그리고 인스턴스에서 mount()는 한번만 붙여준다는 것 기억하세요  

#### 3. data() 
이것은 컴포넌트 인스턴스의 초기 반응상태를 반환하는 함수입니다. 이 함수는 일반 자바스크립트 객체를 반환하며 Vue에 의해 반응하도록 만듭니다.   
인스턴스가 생성되면 반응형데이터 객체를 액세스할 수 있습니다.  https://vuejs.org/api/options-state.html 클릭하시면 더 자세히 알 수 있습니다
