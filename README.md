## Vue3에서의 데이터 종류 정리하고 $data (데이터의 내부) 확인해보기

숫자형, 문자형, 불린형등이 있고, 자바스크립트와 마찬가지로 vue.js에서도 입력된 값에 따라 데이터형이 자동으로 결정됩니다. 

### 문자형, 숫자형,배열, 객체
```html
<h2>데이터형 소개</h2>
<div id="app">
    <p>총가격 {{ myPrice * 1.5}} 원</p>
    <p>{{ "안녕하세요~ "+ myName + "님" }}</p>
    <p>배열 : {{ myArrary }}</p>
    <p>배열의 첫번째 요소 {{ myArrary[0] }}</p>
    <p>메뉴 - {{ myObject.name }}</p>
    <p>가격 -{{ myObject.price }}</p>
</div>
<script>
    const App = {
        data(){
            return {
              myPrice :1000,
            myName:' Hong',
            myArrary:['🍎','🍉','🍇','🍓'],
            myObject :{name:'Coffeee', price :2500}
            }
        }
    }
    Vue.createApp(App).mount('#app')
</script>
```

```html
<h2>데이터형 연습</h2>
<div id="app">
    <p>{{myTea}}</p>
    <p>{{myTea[1].name}} : {{myTea[1].price}}</p>
</div>
<script>
const App = {
  data(){
    return {
    myTea: [
    {name : '다즐링', price: 4000},
    {name: '얼그레이' , price:4500 },
    {name: '카페라떼' , price:3500 }
  ]
    }
  }
}
    Vue.createApp(App).mount('#app')
</script>
```

위의 예제에서 javascript 부분만 아래와 같이 변경해보자.   
``` javascript
<script>
  var teaList = [
        {name : '다즐링', price: 4000},
        {name: '얼그레이' , price:4500 },
        {name: '카페라떼' , price:3500 }
    ]
const App = {
  data(){
    return {
    myTea: teaList
    }
  }
}
Vue.createApp(App).mount('#app')
</script>
```
결과화면을 확인한다.

        
### $data : 데이터의 내부를 확인하고자 할때
```html
<body>
<h2>데이터의 내부를 확인할때</h2>
<div id="app">
    {{ $data }}
</div>
<script>
const App = {
  data(){
    return {
      myTea: [
    {name : '다즐링', price: 4000},
    {name: '얼그레이' , price:4500 },
    {name: '카페라떼' , price:3500 }
  ]
    }
  }
}
Vue.createApp(App).mount('#app')
</script>
</body>
```
결과는 data:{ } 에 정의된 모든 내용이 화면에 출력됩니다.   
<img width="440" alt="스크린샷 2023-02-25 오후 8 53 33" src="https://user-images.githubusercontent.com/48478079/221355444-ca1c4be3-59ce-4d2e-a509-6cd837708da2.png">

