## Vue3에서의 데이터 종류 정리하고 가기

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
    new Vue({
        el:'#app' ,
        data: {
            myPrice :1000,
            myName:' Hong',
            myArrary:['🍎','🍉','🍇','🍓'],
            myObject :{name:'Coffeee', price :2500}
        }

    })
</script>

```

```html
<h2>데이터형 연습</h2>
<div id="app">
    <p>{{myTea}}</p>
    <p>{{myTea[1].name}} : {{myTea[1].price}}</p>
</div>
<script>
    new Vue({
        el:'#app' ,
        data: {
            myTea: [
            {name : '다즐링', price: 4000},
            {name: '얼그레이' , price:4500 },
            {name: '카페라떼' , price:3500 }
            ]
        }

    })
</script>
```

위의 예제에서 javascript 부분만 아래와 같이 변경해보자.   
```javascript
<script>
    var teaList = [
        {name : '다즐링', price: 4000},
        {name: '얼그레이' , price:4500 },
        {name: '카페라떼' , price:3500 }
    ]
    new Vue({
        el:'#app' ,
        data: {
            myTea: teaList
        }
    })
</script>
```


