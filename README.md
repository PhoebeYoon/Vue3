# Vue3 Lesson 를 위해 

#### 속성
```html
<body>
    <nav class="navbar navbar-expand-lg navbar-light bg-list">
        <div class="container-fluid">
            <a href="#" class="navbar-brand">My Vue</a>
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
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



(lesson05 에서 사용했던 예제를 가져와 수정한다)
