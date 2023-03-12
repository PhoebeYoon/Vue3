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
      console.log('From methods -- message')
      return this.user =='kim'? 'Welcome':'Not allowed'
    },
    isActive(){
      console.log('From methods -- active')
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

이제 코드를 조금 추가해 보겠습니다 
``` <input type="text" v-model="user"> ```  
그후  웹페이지를 리로드시키고, 텍스트 상자에 글자를 하나씩 적어봅니다.  
그러면 웹페이지를 리로드할때, 텍스트 상자에 글자를 하나씩 입력할때마다 콘솔창에 
" from methods -- message " 
" from methods -- active " 가 출력되는 것을 확인할 수 있습니다.  
즉 이벤트가 발생하거나 내용이 바뀔때마다 어플리케이션 전체가 재실행되는 것입니다. 이것은 매우 비효율적이라는 것을 알수있습니다.  
 
이제는 computed 속성를 사용해 보겠습니다.  아래의 코드를 추가합니다 

``` html
 computed:{
    com_message(){
      console.log(' --> computed -- messag ')
      return this.user =='kim'? 'Welcome':'Not allowed'
    }
  },
```   
이제 웹페이지를 리로드 한번만  합니다. 아래와 같은 출력을 얻습니다   
<img width="196" alt="스크린샷 2023-03-12 오후 7 29 54" src="https://user-images.githubusercontent.com/48478079/224538910-6d378d3e-0445-45bc-a6dd-d6223160fa90.png">

이제 버튼을 클릭해 봅니다 그러면 ' --> computed -- messag '은 출력되지 않고 methods에 있는 내용만 출력됩니다. 버튼을 여러번 클릭할지라도 ' --> computed -- messag '는 출력되지 않는 것을 확인할 수 있습니다.  (이렇게 결과가 나오셨나요?)  
이제 텍스트상자에 글자를 입력합니다. 입력창에 글자를 입력하면 ' --> computed -- messag '이 콘솔창에 나타납니다.

computed 속성과 methods에 같은 함수를 적용했는데, methods는 여러가지 경우에 모두 반응하고, computed는 지정된 경우에는 반응합니다.
더 자세한 내용은 나중에 알아보기로하고 지금은 이 정도로 이해하시면 될듯 싶습니다

