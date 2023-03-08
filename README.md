##### 🌵 Vue3.js

## 🌵이 과정 통해 여러분은 
1. vue가 무엇인지와 설치방법을 익히게 됩니다.
2. vue의 기초문법을 익히게 될것입니다.
3. 바인딩이 무엇인지 배우며 사용방법을 이해하고 익히게 될것입니다.
4. 어떤 이벤트가 있는지 이벤트를 어떻게 연결시키며 다루는지 배우게 될것입니다.
5. 반복문에 대해 배우면 여러가지 스킬을 습득할 것입니다.
6. 조건문에 대해 배우며 조건의 여러가지 형태에 대해 다룹니다.
7. 폼태그를 다루며 v-model의 수식어에 대해 배웁니다
8. 간단한 계산 프로그램을 짜봅니다. 
9. 매개변수를 전달하는 이벤트에 대해 배웁니다


## 🌵 Vue3에 대해 알아보겠습니다 

### 1. Vue.js란  웹애플리케이션의 사용자 인터페이스를 만들기 위해 사용하는 오픈 소스 프로그레시브 자바스크립트 프레임워크이다.
Vue.js는 고성능의 싱글 페이지 애플리케이션(SPA)을 구축하는데 이용가능하다.
점진적으로 채택 가능한 구조를 갖추고 있다.


### 2. Vue.js는 Single Page Application (SPA, 스파)이다.
서버로부터 완전한 새로운 페이지를 불러오지 않고 현재의 페이지를 동적으로 다시 작성함으로써 사용자와 소통하는 웹 애플리케이션이나 웹사이트를 말한다.
SPA에서 HTML, 자바스크립트, CSS 등 필요한 모든 코드는 하나의 페이지로 불러오거나,[1] 적절한 자원들을 동적으로 불러들여서 필요하면 문서에 추가한다.


### 3. Vue.js의 동작원리 
- 가상 DOM이라는 DOM 트리를 모방한 가벼운 JS 객체를 통해 직접 DOM을 핸들링 하지 않고 자바스크립트가 HTML을 렌더링하는 방법
- 컴포넌트 기반의 프레임워크로 화면을 여러개의 작은 단위로 쪼개어 개발 → 재사용성↑, 구현 속도↑, 코드 가독성↑




### 실습을 위한 환경설정.
1 . 사용할 에디터 설치하기( vs code )
  - html 파일생성시에 기본  lang="en" 아닌 lang='ko' 로 바꾸자
  - vscode > setting(설정) > 검색창 : emmet 엔터 > 스크롤다운해서 아래쪽으로 >   
    <b> Emmet:Variables </b> 찾기 > 항목 : lang : 값: ko 변경하면 끝
  - vscode 실행하고 >  파일이름.html 만들고 > 나타나는 화면에서 '<b>doc</b>' 엔터 하면 기본코드가 쭈~욱 나옵니다   
  - voscode 의 확장기능 중 Live Server , Vetur(_코드별로 하이라이트가 됩니다, 하지만 없어도 무방_)를 설치하면 편해요   
<img width="190" alt="스크린샷 2023-02-24 오전 10 06 23" src="https://user-images.githubusercontent.com/48478079/221066923-e4dea5f0-f6b1-4a08-bb5b-d5ed3bc95f85.png"> <img width="190" alt="스크린샷 2023-02-24 오전 10 06 42" src="https://user-images.githubusercontent.com/48478079/221066936-82e1d9d9-0047-4a21-87c6-a960cb269f91.png"> <img width="210" alt="스크린샷 2023-02-24 오전 10 06 01" src="https://user-images.githubusercontent.com/48478079/221066951-3ac96bc4-ef98-442b-be27-250d74e9a495.png">

2.  vue.js설치하기    
  - html 안에 삽입하여 사용하려면  
   ``` https://developer.mozilla.org/ko/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_getting_started ``` 사이트 방문
  - CDN 방식으로 가져오기(개발용)으로 가져와 
     ``` <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>``` 를 html 페이지에 복사붙여넣기한다.  
   - 혹 npm 에 대한 경험이 있다면, 
     ``` npm install --global @vue/cli   ``` 시도해 보자  
3. 아래와 같이 하여 실행되는지 확인해 보자
```html
 <!-- index.html -->
      <html lang="ko">
      <head>
          <meta charset="UTF-8">
          <meta http-equiv="X-UA-Compatible" content="IE=edge">
          <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
          <title>Learning Vue</title>
      </head>
      <body>
          <h1>Hello Vue world</h1>
          <script src="app.js"></script>
      </body>
      </html>
```
```javascript
<!-- app.js -->
console.log('welome to vue world')
```
4. 크롬 브라우저에서 개발자도구를 열고 console 창을 확인해 보자  -끝-

:cactus: ``` https://vuejs.org/examples/ ```  방문하면 vue로 작성된 샘플들을 볼 수 있다
