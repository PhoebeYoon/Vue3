## v-bind
{{ }}를 이용하여 데이터를 화면에 표시하는 것이 가능한것을 보았다. 여기있는 v-bind는 html태그의 속성을 데이터로 지정할때 사용된다.


#### :link, :href ,:title
```html
<body>
    <nav>
        <div>
            <a href="#">My Vue</a>
            <ul>
                <li v-for="link in links" class="nav-item">
                    <a href="#" class="nav-link">{{ link.text }} </a> # 여기를 수정
                </li>
            </ul>
        </div>
    </nav>
    <div id="content" class="container">
        <h1>{{pageTitle}}</h1>
        <p>{{pageContent}}</p>
    </div>

    <script>
        Vue.createApp({
            data(){
                return {
                    links:[
                        {text:"Home", url:'home.html'},
                        {text:"About", url:"about.html"},
                        {text:'Contact',url:'contact.html'}
                    ]  #여기를 수정
                }
            }
        }).mount('nav');
        Vue.createApp(
            {
                data() {
                    return {
                        pageTitle:'Hello, Vue ',
                        pageContent : 'Welcome to wonderful world'
                    }
                }
            }
        ).mount('#content');
    </script>
```
( 실습할때는 #기호로 들어간것을 제거해 주세요 )
위의 내용이 작동되는지 확인한 후에 <a>태그 부분만 아래처럼 수정해보자.   
``` html 
<a href="{{link.url}}">{{ link.text }} </a>
```
정상적으로 출력되는것처럼 보이지만 개발자도구를 보면,  <b>link.url </b>가 'home.html' 바뀌지 않은 것을 볼수있다.   
<img width="422" alt="스크린샷 2023-02-25 오후 1 50 01" src="https://user-images.githubusercontent.com/48478079/221338934-c9068610-92c4-4e1d-8fdd-615196b0aca1.png">

 ```html
  <a v-bind:href="link.url" class="nav-link">{{ link.text }} </a> 
  ``` 
 v-bind를 삽입하고 {{ }}는 빼고 v-bind:href="link.url" 수정하면 결과가 정상적으로 나온다. 어플리케이션에서 html속성을 사용하겠다는 의미로 <b>v-bind:</b>를 적고 속성을 적어준다. 그리고 <b>속성의 값은 자바스크립트표현식 </b>이 와야하기 때문에 {{ }} 는 없애준다. v-bind는 굉장히 많이 사용하는 속성이기 때문에 'v-bind:' 를 간단히 ':' 으로 대치해서
    
 ```html
  <a :href="link.url" >{{ link.text }} </a> 
  ``` 
  이렇게 적는다  
  이제 조금더 내용을 바꿔보자.  
 ```html
  <li v-for="link in links" >
  <a class="nav-link"  :href="link.url"  :title="`This 페이지는 ${link.url}로 이동`">{{ link.text }} </a>
 </li>   
  ``` 
  
 <img width="629" alt="스크린샷 2023-02-25 오후 2 20 10" src="https://user-images.githubusercontent.com/48478079/221340034-2fe50e28-675e-4ab7-b828-49385db9a2be.png">

#### v-bind:disabled 
```html
div id="app">
  <button v-bind:disabled>Press</button> 
  <button v-bind:disabled="true">Click</button>
  <button v-bind:disabled="false">Enter</button>
</div>    
<script>
Vue.createApp({
  data(){
    return {
    }
  }
}).mount('#app')
</script>

```    

#### :src

```html
<script src="https://unpkg.com/vue@next"></script>
<div id="app">
       <img v-bind:src="src" v-bind:alt="alt"/><br>
       <a v-bind:href="link">Naver</a> 
       <p v-text="myText"></p>
       <p v-html="myHtml"></p>
</div>
<script>
    const App = {
        data(){
            return {
              src:'https://picsum.photos/200/300',
              alt:'아무거나',
              link:'http://www.naver.com',
              myText:'Hello guys !!',
              myHtml:'<strong>My html</strong>'
            }
        }
    }
    Vue.createApp(App).mount('#app')
</script>

```


