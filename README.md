:cactus: Vue3 Lesson 

## radio 버튼

```html
<div id="app">
  <input type="radio" value="red"   v-model="colors">빨강
  <input type="radio" value="blue"  v-model="colors">파랑
  <input type="radio" value="green" v-model="colors">초록
  <p>선택하신 색상은 {{ colors }} 입니다</p>
</div>
<script>
Vue.createApp({
data(){
  return { colors:'red' }
}
}).mount("#app")
```   
여기서 html에서 폼태그의 내용 작동방법을 상기시켜보자. 색상3개는 마치 하나짜리 구성으로 red, blue, green이 따로 작동하는 것이 아니라, 3개중 1개만 선택하게 만들기위해 name 속서에 같은 이름을 준다. 그래야    
red를 선택하면 blue, green이 선택되지 않고,   
blue를 선택하면 선택되어 있던 red가 자동으로 해제되어  
green를 선택하면 blue, red가 모두 해제된 상태가 된다.   
이것이 일반 html에서의 작동방법일 것이다. 하지만 vue에서는 name 속성을 지정하지 않았지만 3개 중 1개만 유일하게 선택되어진다는 것을 알수있다.
