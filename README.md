##### 🌵 Vue3.js

## v-model에서 사용할 수 있는
### .lazy .number .trim 에 대해 알아보겠습니다.

``` html
<div id="app">
  <form v-on:submit.prevent="formHandler">
    <label>Name:</label>
    <input type="text" v-model="formData.name" placeholder="길동"/>
    <button type="submit"> Submit </button>
  </form>
  <p>{{ formData.name}}</p>
</div>
<script>
Vue.createApp({
  data(){
    return {
      formData:{
        name:'',
        lastname:'',
        age:'',
        checked:false
    }
    }
  },
  methods:{
    formHandler(){
    }
  }
}).mount("#app")
</script>

````   
이렇게 만들어놓고 시작하겠습니다.  

실행화면에서 input태그에 글자를 하나씩 적으면 ``` {{ formData.name}}  ``` 이라는 곳에 한글자씩 출력됩니다.   
그런데 내용을 다 적은 후에 전체내용을 나오게 하고자 한다면 어떻게하면 될까요?   
바로, .lazy를 사용하시면 됩니다.   실행해 보겠습니다.
```<input type="text" v-model.lazy="formData.name" placeholder="길동"/> ```이렇게 변경해 줍니다.   
그리고 내용을 입력하면, 입력 중일때는 출력되지 않다가 사용자가 입력창을 벗어났을때 비로서 입력된 내용이 출력되는 것을 확인할 수 있습니다.

이제 .number를 해 보겠습니다.  아래와 같이 내용을 바꾸겠습니다.  
```
<label>Age:</label>
<input type="text" v-model="formData.age"/>
<p>{{ formData.name}} , {{ formData.age}} 살 </p>
```
우리가 하려고 하는 것은 나이를 입력했을때 입력된 내용이이 문자인지 숫자인지를 먼저 알아내고자 합니다. 그래서 나이에 +1를 해줄것입니다.  
<b>.number를 사용하기전에 살짝 착각하기 쉬운것을 언급하고자 합니다 </b> 만약 여러분이   
``` <p>{{ formData.name}} , {{ formData.age +1 }} 살 </p> ``` {{ 여기에 더하기 1 }} 한다면 .number를 사용하지 않아도 입력된 숫자에 +1이 되어서 출력됩니다.  
그러면 " 어, .number를 사용할 필요가 없네! 자동으로 숫자로 바뀌었으니까 더하기 1이 됐잖아" 라고 하실 수 있습니다. Vue는 자바스크립트 프레임워크라는 것을 잊지마세요. 

``` javascript
methods:{
    formHandler(){
      console.log(this.formData.name)
      console.log(this.formData.age + 1);
    }
  }
```   
를 하고 콘솔창에 찍어보면 그렇지 않다는 것을 알 수 있습니다. 만약 입력창에 '33'을 입력하면 콘솔창에는 '331' 이라고 나옵니다.
이제 이해됐다면, 
```<input type="text" v-model.number="formData.age"/> ```로 변경해서 실행해보세요. 콘솔창에 34라고 출력됩니다. 

이와같이 이번에는 
``` 
<input type="text" v-model="formData.name" placeholder="길동"/> 
```   
로 내용을 확인한다면 실행화면에서 입력할때 일부러 공백을 넣어줍니다 그럼 콘솔창에는 공백이 그대로 유지된채 콘솔창에 출력됩니다.   
``` v-model.trim="formData.name"  ```  ,  ```  console.log("*"+this.formData.name+"*") ``` 으로 변경하고 아까처럼 실행화면에서 공백을 주고 입력해 보겠습니다. 
이번에는 공백이 제거된채 콘솔창에 출력됩니다. 내용에 공백제거를 확인하기 위해 별표를 앞뒤로 넣었습니다  






