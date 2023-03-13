##### 🌵 Vue3.js


## watch 속성에 대해 
watch 속성은 특정 데이터의 변화를 감지하여 자동으로 특정 로직을 수행해주는 속성입니다.

```html
 <div id="app">
    <input v-model="user"/>
    <button v-on:click="toggleActive">Other action</button>
    <hr/>
    <div> Message: {{ compMessage }}</div>
    <div> Active: {{ compActive }} </div>
</div>
<script>
Vue.createApp({
  data(){
  return { 
    user:'',
    active:false
  }
  },
  watch:{
    active1(){
      console.log('watch start')
    }
  },
  computed:{
    compMessage(){
      console.log('COMPUTED MESSAGE')
      return this.user === 'Francis' ? 'Welcome' : 'Now allowed'
  },
    compActive(){
      console.log('COMPUTED ACTIVE')
      return this.active ? 'Active':'Not active'
  }
},
methods:{
  toggleActive(){
        this.active = this.active ? false : true
    }
}
}).mount("#app")
</script>
``` 

위의 예제에서 웹페이지를 리로드하면 'COMPUTED MESSAGE' 와 'COMPUTED ACTIVE'가 콘솔창에 나타나지만 wathc에 선언된 내용을 나오질 않습니다.   
이제 텍스트상자에 아무내용을 넣고 버튼을 클릭하면 'watch start'가 나옵니다. 왜냐하면 data()에서 active:false 로 설정되어 있습니다. 버튼을 클릭하면 toggleActive()가 실행되면서 active의 값을 변경합니다.    
이때 watch:{  }에서는 active의 값을 지켜보고 있다가 변경이 되는 것을 감지하고 선언된 내용을 실행하는 것입니다. 그래서 콘솔창에 'watch start'라는 것이 출력되는 것입니다. 
