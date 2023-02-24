## Using Loops

``` html
<body>
    <nav class="navbar navbar-expand-lg navbar-light bg-list">
        <div class="container-fluid">
            <a href="#" class="navbar-brand">My Vue</a>
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li class="nav-item">
                    <a href="#" class="nav-link">Home</a>
                </li>
                <li class="nav-item">
                    <a href="#" class="nav-link">About</a>
                </li>
                <li class="nav-item">
                    <a href="#" class="nav-link">Contact</a>
                </li>
            </ul>
        </div>
    </nav>
    <div id="content" class="container">
        <h1>{{pageTitle}}</h1>
        <p>{{pageContent}}</p>
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
        ).mount('#content');
    </script>
</body>

```

여기서 다른 vue 인스턴스를 만들어보자. 아래 코드를 js부분에 추가한다  
```javascript
Vue.createApp({
            data(){
                return {
                    links:['Home','About','Contact']
                }
            }
        }).mount('nav');
```
그리고 li태그 부분을 아래와 같이 수정한다 
```html
<li class="nav-item"> <a href="#" class="nav-link">{{links[0]}}</a></li>
<li class="nav-item"> <a href="#" class="nav-link">{{links[1]}}</a></li>
<li class="nav-item"> <a href="#" class="nav-link">{{links[2]}}</a></li>
```
