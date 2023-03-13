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

