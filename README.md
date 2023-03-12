##### 🌵 Vue3.js

## computed에 대해 알아보겠습니다.
이것은 언뜻보면 methods와 똑같다. 그렇다 사용방법도 선언하는 방법도 거의 똑같다. 그래서 왜 computed를 사용하는지 알아야 하는 것이다

우선 실습하기 전에 2가지만 기억하자.   
computed는 함수형 속성이고 
methods는 렌더링이 일어날때마다 항상 실행된다.

아래의 코드를 만들고 시작해보자.   
``` html
 <div id="app">
    <button @click="toggleActive">action</button>
    <div> message : {{ message()}}</div>
    <div> active {{ isActive() }} </div>
  </div>
<script>
Vue.createApp({
  data(){
  return { 
    user:'',
    active:false
  }
  },
  methods:{ 
    message(){
      console.log('message')
      return this.user =='kim'? 'Welcome':'Not allowed'
    },
    isActive(){
      console.log('active')
      return this.active? 'Active':'Not active'
    },
    toggleActive(){
      this.active = this.active? false:true
    }
  }
}).mount("#app")
</script>
```

위의 내용을 완성한 후에 웹페이지를 리로드하면 콘솔창에 'message','active'출력되고, 또 버튼을 클릭할때마다 콘솔창에 'message','active' 가 출력되는 것을 확인하세요. 


