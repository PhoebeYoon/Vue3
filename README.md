
이전 수업을 이어서 진행합니다. 아래의 코드를 실행해보세요. 에러없이 작동되는지 웹브라우저로 확인해 보세요 
``` html
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>

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
mount(css 셀렉터)인데 클래스나 다른 것은 여러개일 수 있어서 혼동될 수 있으니 유일한 의미를 갖는 아이디를 사용하는 것이라고 말씀드렸죠! <b> #container </b> 입니다
여기서 브라우저의 개발자도구를 열어 어떤 변화가 있는지 조금만 확인해보세요.

<img width="435" alt="스크린샷 2023-02-24 오후 8 07 09" src="https://user-images.githubusercontent.com/48478079/221164464-b2a098be-1c0e-44e5-bdf0-dafa17751b02.png">

이미지에서 'data-v-app'를 찾아보고, script 내용을 바꿔보도록 하겠습니다.  
``` html
<script>
        Vue.createApp(
            {
                data() {
                    return {
                        
                    }
                }
            }
        ).mount('#container')
    </script>
```
여기에 내용을 추가해 보자   

``` html
<div id="container">
        <h1>{{ pageTitle }}</h1>
        <p>
            {{ pageContent}}
        </p>
    </div>
    <script>
        Vue.createApp(
            {
                data() {
                    return {
                        pageTitle:'Hello, Vue ',
                        pageContent : 'Welcome to wonderful world'
                    }
                }
            }
        ).mount('#container')
    </script>
```
결과가 제대로 나왔다면 축하합니다 ~~ 이제 기본적인 구조는 이해하신것입니다.  lesson04_Vue2_Vue3 으로 넘어가세요 
