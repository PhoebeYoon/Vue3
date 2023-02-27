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
이것이 일반 html에서의 작동방법일 것이다. 하지만 vue에서는 name 속성을 지정하지 않았지만 3개 중 1개만 유일하게 선택되어진다는 것을 알수있다. 여러개의 라디오버튼에 v-model="같은 프로퍼티명"를 지정하면 이렇게 작동된다.  

## radio 버튼으로 이미지를 바꿔보자 (컵케이크 또는 피자 뭘 먹을까 )
```html
<div id="app">
  <input type="radio" v-model="fileName" value='./img/cupcake.png'>컵케이크
  <input type="radio" v-model="fileName" value='./img/pizza.png'> 피자 
<p> <img v-bind:src="fileName" > </p>
</div>
<script>
Vue.createApp({
data(){
  return { fileName:''}
}
}).mount("#app")
</script>
```

## select 문
```html
<div id="app">
  <select v-model="selectColor">
    <option value="" >원하는 색을 선택하세요</option>
    <option value="red">Red</option>
    <option value="blue">Blue</option>
    <option value="green">Green</option>
  </select>
  <p v-bind:style="{ backgroundColor: selectColor }">선택하신 색상은 {{ selectColor}}입니다</p>
</div>
<script>
Vue.createApp({
data(){
  return {  selectColor:''}
}
}).mount("#app")
```

#### :coffee: 여기서 잠깐
> 이제까지의 설명으로 '{{ }}'는 알겠는데, ``` <p v-bind:style="{ backgroundColor: selectColor }``` 에서 갑자기 나오는 { } 하나짜리는 뭐지? 하실분이 있을 듯해서 짧게 설명드릴께요.  <b>{ 키:값 } </b>는 객체표현에 사용되는거죠. 자바스크립트하셨다면 기억나실거예요. 그리고 lesson06에서,  
  ``` <a v-bind:href="link.url" class="nav-link">{{ link.text }} </a>  ``` 을 다시 살펴보면,    
  ' v-bind:속성="속성값" '지정되어 있습니다. 그런데 위의 예제에서는 "속성값" 아니라 <b>{ 자바스크립트표현식: 속성값 } </b>으로 되어있습니다. 그러니까 <b>객체형식의 키와 값 </b>으로 표현한 것이죠. 태그안에 'v-bind:'를 적어서 Vue의 디렉티브 속성을 사용하겠다고 했으니 Vue가 알아듣는 표현식을 사용해야하는데 vue는 자바스크립트표현식을 이해할 수 있으니, css표현인 'background-color'가 아닌 자바스크립트 표현인 'backgoundColor'를 적은것이고 그 값으로 data에 선언된 변수를 준 것입니다. 
또한, background-color: {selectColor} 로 주면 안되나 싶기도 하지만 앞에 v-bind: 가 있으니 css표현을 사용하면 에러가 발생합니다.
  
  
### 여러개를 선택하는 select문  
```html
div id="app">
  <select multiple v-model="selectColor">
    <option value="">원하는 색을 선택하세요</option>
    <option value="red">Red</option>
    <option value="blue">Blue</option>
    <option value="green">Green</option>
    <option value="orange">Orange</option>
    <option value="purple">Purple</option>
    <option value="brown">Brown</option>
  </select>
  <p>선택하신 색상은 {{ selectColor}}입니다</p>
</div>
<script>
Vue.createApp({
data(){
  return {  selectColor:[]}
}
}).mount("#app")  
```
  여러개를 선택하기 위해서는 data에 selectColor:<b>'   '</b> 대신 <b>[ ]</b>를 지정해야 합니다. 그리고  목록선택시 shift키를 사용하여 여러항목을 선택하면 됩니다.
  
  
