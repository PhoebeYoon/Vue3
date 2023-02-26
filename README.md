:cactus: Vue3 Lesson 

## v-on 디렉티브에서 키보드의 키를 사용할때

키보드의 키가 입력될 때 Vue인스턴스의 메소드를 실행하도록 한다. 이때 어떤 키가 입력되었는지 지정해 주어야 한다. 그렇지않으면 아무키나 입력해도 메소드가 실행되어 버리기 때문이다. 특정키를 입력했을 때 반응하도록 하기 위해 키수식자를 저정한다.

|키수식자|    |     |
|:----:|:----:|:----:|
|.enter|.down|.tab|
|.left|.delete|.right|
|.esc|.space|.up  |
|.48~.57(0~9)|.65~.90(A~Z)|    |
|시스템|수식자키 | |
|.alt|.shift|.ctrl|
|.meta |  |  |

```
<input v-on:keyup.키수식자="메소드명">
```
### enter 키를 사용
```html
<h2> v-on 디렉티브 / 키수식자</h2>
<div id="app">
  <input v-on:keyup.enter="showAlert" type="text">
</div>
<script>
Vue.createApp({
data(){ 
      return { } 
  },
methods:{
  showAlert:function(){
    alert("Enter키를 눌렀습니다")
  }
}
}).mount('#app')
</script>
```

### shift + enter 키를 함께 사용 
``` html
<h2> v-on 디렉티브 / 키수식자</h2>
<div id="app">
  <input v-on:keyup.enter.shift="showAlert" type="text">
  <p>{{ mytxt }}</p>
</div>
<script>
Vue.createApp({
data(){ 
      return { mytxt :'텍스트상자를 클릭한 후 shift + enter를 함께 누르세요'} 
  },
methods:{
  showAlert:function(){
    alert("Shift키와 Enter키를 눌렀습니다")
  }
}
}).mount('#app')
</script>

```
