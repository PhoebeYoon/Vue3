##### 🌵 Vue3.js


## 수업소개

### 여러분은 아래의 내용들을 학습하게 될 것입니다.

1. 기초들 ( Basics )
- Data
- Methods
- Computed
- Directives
- Modifier
- Events
- Watchers

2. More Pro way
- CLI
- components
- lifecycles
- props
- transitions
- form
- vuex
- authentication
- database

### 빠른 시작을 해보자
1. CDN 사용. 
 a. vs code를 열고 'test.html' 문서를 만듭니다. 문서의 첫줄에 'doc'입력하고 엔터 -> 그러면 자동완성으로 기본코드가 완성됩니다.  
 b. script 태그안에 ``` <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>  ``` 을 삽입합니다.   
 c. 문서의 다른 곳에 아래의 코드를 삽입합니다  
 ``` html
<div id="app">{{ message }}</div>

<script type="module">
  import { createApp } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js'

  createApp({
    data() {
      return {
        message: 'Hello Vue!'
      }
    }
  }).mount('#app')
</script>
```     
d. 위의 test.html를 웹브라우저로 엽니다. 'Hello Vue! '가 출력되는지 확인합니다.


 ### 수업에 임하는 우리의 자세 : 
 아는 것은 쉽다. 모르는것은 어렵다. 아는 길은 여러번 해 보는 것이다. 

### 우리의 수업은 레시피를 따라 먼저하고, 응용은 나중에 합니다
처음에는 라면봉지 뒤에 적혀있는 '레시피'처럼 필요한 정해진 내용을 먼저 학습한 뒤에 문접과 vue에 친해진 다음 응용을 할 것입니다

