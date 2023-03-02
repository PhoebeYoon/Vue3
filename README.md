# Vue3 Lesson 를 위해 
## Vue.js란 사용자 인터페이스를 만들기 위한 프론트엔드 자바스크립트 프레임워크입니다.
### 이 학습을 통해 여러분은 
1. vue가 무엇인지와 설치방법을 익히게 됩니다.
2. vue의 기초문법을 익히게 될것입니다.
3. 바인딩이 무엇인지 배우며 사용방법을 이해하고 익히게 될것입니다.
4. 어떤 이벤트가 있는지 이벤트를 어떻게 연결시키며 다루는지 배우게 될것입니다.
5. 반복문에 대해 배우면 여러가지 스킬을 습득할 것입니다.
6. 조건문에 대해 배우며 조건의 여러가지 형태에 대해 다룹니다.
7. ㅇㅇㅇ
8. 간단한 계산 프로그램을 짜봅니다.
9 매개변수가 있는 이벤트에 대해 다룹니다

## Vue.js의 특징
- SPA ( Single Page Application)



#### 첫번째 시도는 이렇게 해보자.
1 . 사용할 에디터 :  vs code
  - html 파일생성시에 기본  lang="en" 아닌 lang='ko' 로 바꾸자
  - vscode > setting(설정) > 검색창 : emmet 엔터 > 스크롤다운해서 아래쪽으로 >   
    <b> Emmet:Variables </b> 찾기 > 항목 : lang : 값: ko 변경하면 끝
  - vscode 실행하고 >  파일이름.html 만들고 > 나타나는 화면에서 '<b>doc</b>' 엔터 하면 기본코드가 쭈~욱 나옵니다   
  - voscode 의 확장기능 중 Live Server , Vetur(_코드별로 하이라이트가 됩니다, 하지만 없어도 무방_)를 설치하면 편해요   
<img width="190" alt="스크린샷 2023-02-24 오전 10 06 23" src="https://user-images.githubusercontent.com/48478079/221066923-e4dea5f0-f6b1-4a08-bb5b-d5ed3bc95f85.png"> <img width="190" alt="스크린샷 2023-02-24 오전 10 06 42" src="https://user-images.githubusercontent.com/48478079/221066936-82e1d9d9-0047-4a21-87c6-a960cb269f91.png"> <img width="210" alt="스크린샷 2023-02-24 오전 10 06 01" src="https://user-images.githubusercontent.com/48478079/221066951-3ac96bc4-ef98-442b-be27-250d74e9a495.png">

2.  vue.js 를 html 페이지에 삽입하기
  - ``` https://developer.mozilla.org/ko/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/Vue_getting_started  사이트로 방문 ```
  - CDN 방식으로 가져오기(개발용):    
     ``` <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>``` 를 html 페이지에 복사붙여넣기한다. 혹 npm 에 대한 경험이 있다면, 
     ``` npm install --global @vue/cli   ``` 시도해 보자  
3. 크롬 브라우저를 실행하고 확장프로그램에 <b> Vue Devtools</b> 를 설치해 보자.  
    
4. 
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
5. 크롬 브라우저에서 개발자도구를 열고 console 창을 확인해 보자  -끝-

:cactus: ``` https://vuejs.org/examples/ ```  방문하면 vue로 작성된 샘플들을 볼 수 있다
