:cactus: Vue3 Lesson 

### Vue2 vs Vue3 비교하기
이제까지 내용을 이해했다면 그동안 알게모르게 사용했던 문법을 잠깐 정리하자.  
모양이 다르지만 우리는 이미 모두 잘 작동한다는 것을 경험했다. 

#### Vue2으로 표현
```
const app = new Vue({
  el: '#app'
  data:
  {
        object: <some object>
  }
})
```

#### Vue3으로 표현
```
const app = Vue.createApp({  
data(){
      return {
          object: <some object or string etc>
    }
  }
})
```
또한 data: 와 data()가 자바스크립트의 es5버전과 es6버전의 차이라는 것도 알아봤다. vue는 자바스크립트 프레임워크이기 때문에 자바스크립트의 문법이 적용된다.  
여기서 우리가 알고 싶은 내용 중 중요한 것 하나는, 위의 두개의 문법이 모두 잘 작동하지만,  이따금 '~ Vue is not a constructor ~' 오류가 뜬다는 것이다. 왜 그럴까?   

이것은 Vue 라이브러리를 가져와 코드를 해석하는 방식인, CDN 방식과 Vue3, Vue2의 차이 때문이다.  
예를 들면,
위에 있는 Vue3 방식대로 Vue 인스턴스를 생성했다고 가정하자. 아래의 코드처럼 작성하면,   
```html
<script src="https://cdn.jsdelivr.net/npm/vue@2.6.0/dist/vue.js"></script>
<div id="app">  {{ msg }}</div>
<script>
new Vue({
  el: '#app',   
  data: { msg :'작동완료' }
	})
		</script>
``` 
Vue생성자를 사용한 것이며 cdn에서는 Vue 생성자를 지원하고 있으므로 코드를 정상적으로 내용을 출력한다.  
이제, 위의 코드에서 생성자를 지원하지 않는   
```<script src="https://unpkg.com/vue@3.0.0"></script> ``` 으로 바꾸어보자.   
그러면, ```  Uncaught TypeError: Vue is not a constructor ``` 가 발생한다.  
그럼, vue3 라이브러리에 맞춰서 내용을 번경해보자.   
```html
<script src="https://unpkg.com/vue@3.0.0"></script>
<div id="app">  {{ msg }}</div>
<script>
    Vue.createApp({
        data() {
            return { 
            msg:'작동 완료'
            }
        }
    }).mount('#app')
</script>
```
결과가 정상적으로 출력된것을 볼 수 있다. 


