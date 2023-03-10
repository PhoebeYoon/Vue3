##### 🌵 Vue3.js


## javascript 표현들 
``` javascript
{{ number + 1 }}
{{ ok ? 'YES' : 'NO' }}
{{ message.split('').reverse().join('') }}
<div :id="`list-${id}`"></div>
```  
이와같은 표현식은 현재 컴포넌트의 인스턴스의 데이터범위로써 평가됩니다.
각 바인딩은 하나의 식만 포함할 수 있습니다. 표현식은 값으로 평가할 수 있는 코드조각으로 간단히 'return' 후에 사용할 수 있는지를 보면됩니다.  그러므로 아래와 같은 표현은 작동하지 않습니다.   
```
{{ var a = 1 }}  <- 이것은 문장이며 표현식이 아닙니다.
{{ if (ok) { return message } }}  <- 이런 흐름제어는 작동하지 않습니다
```

간단히 실습해 봅시다.  
``` html
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>

    <title></title>
</head>
<body>
  <div id="app">
    <p>{{ gretting }}</p>
    <p> Is it true:{{ isItTrue ? 'Yes':'No' }}</p>
    <p>{{ array[0] }}</p>
    <p>{{ obj.car }}</p>
    p>{{ obj[car] }}</p> # 자바스크립트표현이 가능하므로 이것도 가능
    <p>{{ func() }}</p>
  </div>
  <script>
  const date = new Date().toLocaleString()
   const App = {
    data(){
      return {
        gretting:'Hello guys today is ' + date,
        isItTrue: true,
        array:['Francis','Jane'],
        obj:{
            car:'Ferrari'
        },
        func:()=>{
            return 'Message from function'
        }
      }
    }
    }
    Vue.createApp(App).mount('#app')
  </script>
</body>
</html>
```



## 이제 Directives에 대해 보도록 하겠습니다 
디렉티브는 v- 접두사를 사용하는 특수 특성입니다. v-html, v-bind, v-for, v-on, v-slot 등이 있습니다.
전체적인 지시구문은 아래 그림과 같습니다. 

<img width="560" alt="스크린샷 2023-03-10 오후 1 54 55" src="https://user-images.githubusercontent.com/48478079/224226906-d258d88c-06f6-47ed-a27d-d5d9da146349.png">   
[발췌] https://vuejs.org/guide/essentials/template-syntax.html#directives 


## v-text
엘리먼트의 문자 내용을 업데이트합니다.
```javascript
<span v-text="msg"></span>
<span>{{msg}}</span>
```

## v-html
엘리먼트의 innerHTML를 업데이트합니다. 스트링형태입니다
```javascript
<div v-html="html"></div>
```

## v-show
표현식의 결과가 true /false 냐에 따라 엘리먼트가 보이거나 감추어집니다.


## v-if
표현식의 결과가 true /false 냐에 따라 엘리먼트나 템플릿를 렌더링합니다

## v-else
v-if 또는 v-if / v-else-if 체인에 대한 "else 블록"을 나타냅니다
``` javascript
<div v-if="Math.random() > 0.5">
  Now you see me
</div>
<div v-else>
  Now you don't
</div>

```
``` javascript
<div v-if="type === 'A'">
  A
</div>
<div v-else-if="type === 'B'">
  B
</div>
<div v-else-if="type === 'C'">
  C
</div>
<div v-else>
  Not A/B/C
</div>
```
## v-for
소스데이터를 기준으로 엘리먼트나 템플릿을 여러번 렌더링합니다. Array | Object | number | string | Iterable 이 사용됩니다.

```javascript
<div v-for="item in items">
  {{ item.text }}
</div>


<div v-for="(item, index) in items"></div>
<div v-for="(value, key) in object"></div>
<div v-for="(value, name, index) in object"></div>


<div v-for="item in items" :key="item.id">
  {{ item.text }}
</div>

```
## v-on 
엘리먼트의 이벤트리스너를 연결합니다. 간단히 '@'를 사용합니다. 매개변수로는 event 를 사용합니다.
.stop - 이벤트를 호출합니다.stopPropagation().   
.prevent - event.preventDefault()를 호출합니다.   
.timeout - 캡처 모드에서 이벤트 수신기를 추가합니다.   
.self - 이벤트가 이 요소에서 발송된 경우에만 처리기를 트리거합니다.   
.{keyAlias} - 특정 키에 대해서만 핸들러를 트리거합니다.   
.once - 핸들러를 한 번만 트리거합니다.   
.left - 왼쪽 버튼 마우스 이벤트에 대한 트리거 핸들러만 해당합니다.   
.right - 오른쪽 버튼 마우스 이벤트에 대한 트리거 핸들러만 해당합니다.   
.middle - 중간 버튼 마우스 이벤트에 대한 트리거 핸들러만 해당합니다.    
.passive - {passive:true}의 DOM 이벤트를 연결합니다.    
아래의 내용을 그냥 눈으로 쭈욱 보세요 

```
## v-bind
하나 또는 그 이상의 속성 이나 컴포넌트의 속성을 표현식에 동적으로 바인딩시킵니다   
간단히  콜론(:) 이나 (.) (prop modifier를 사용)를 사용합니다 
자세한 내용은  아래 링크를 꼭 클릭해서 살펴보세요   
https://vuejs.org/api/built-in-directives.html#v-text   

``` javascript
<!-- bind an attribute -->
<img v-bind:src="imageSrc" />

<!-- dynamic attribute name -->
<button v-bind:[key]="value"></button>

<!-- shorthand -->
<img :src="imageSrc" />

<!-- shorthand dynamic attribute name -->
<button :[key]="value"></button>

<!-- with inline string concatenation -->
<img :src="'/path/to/images/' + fileName" />

<!-- class binding -->
<div :class="{ red: isRed }"></div>
<div :class="[classA, classB]"></div>
<div :class="[classA, { classB: isB, classC: isC }]"></div>

<!-- style binding -->
<div :style="{ fontSize: size + 'px' }"></div>
<div :style="[styleObjectA, styleObjectB]"></div>

<!-- binding an object of attributes -->
<div v-bind="{ id: someProp, 'other-attr': otherProp }"></div>

<!-- prop binding. "prop" must be declared in the child component. -->
<MyComponent :prop="someThing" />

<!-- pass down parent props in common with a child component -->
<MyComponent v-bind="$props" />

<!-- XLink -->
<svg><a :xlink:special="foo"></a></svg>

```
## v-model 
양식 입력 요소 또는 구성 요소에 양방향 바인딩을 만듭니다.  
``` javascript
<input>   
<select>    
<textarea>   
components 에 한정되어 사용됩니다   
.lazy - 입력대신 이벤트의 변화를 감지합니다    
.number - 스트링을 숫자로 변경합니다  
.trim - 공백을 제거합니다  
```
    
## v-slot   
간단히 '#'를 사용합니다. 컴포넌트의 Slots 도 있습니다.

## v-pre
## v-once
## v-memo

더 자세한 내용을 실습을 통해 살펴보도록 하겠습니다. 


