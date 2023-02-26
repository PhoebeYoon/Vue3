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
