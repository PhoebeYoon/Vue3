### lesson 03

``` html
<div id="container">
        <h1>Hello, Vue</h1>
        <p>
            Welcome to wonderful world
        </p>
    </div>
    <script>
        Vue.createApp().mount('#container');
    </script>
```
mount(css 셀렉터)인데 클래스나 다른 것은 여러개일 수 있어서 혼동될 수 있으니 유일한 의미를 갖는 아이디를 사용하는 것이다 그래서 <b>#아이디</b> 이다.
여기서 브라우저의 개발자도구를 열어 어떤 변화가 있는지 조금만 확인해보자   
<img width="435" alt="스크린샷 2023-02-24 오후 8 07 09" src="https://user-images.githubusercontent.com/48478079/221164464-b2a098be-1c0e-44e5-bdf0-dafa17751b02.png">

이미지에서 'data-v-app'를 찾아보자.

