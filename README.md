## 꼭 el:#app 이것만 써야하는건가

```html
<ul class="foo">
    <li class="bar" v-bind:style="insertStyle1">This is red text {{ msg1 }}</li>
    <li class="foo" v-bind:style="insertStyle2">This text is blue {{ msg2 }}</li>
</ul>

<script>
    new Vue({
        el:'.bar',
        data: {
            insertStyle1:'color:red',
            msg1:'bar'
        }
        });

    new Vue({
        el:'.foo',
        data:{
            insertStyle2:'text-decoration:underline',
            msg2:'foo'
        }
    });
</script>
```
결과를 확인해보자

<img width="207" alt="스크린샷 2023-02-25 오후 9 08 12" src="https://user-images.githubusercontent.com/48478079/221356050-46de7ff1-6538-46cc-9088-18cdaa5e02a4.png">   
개발자도구를 확인해보면, 

<img width="479" alt="스크린샷 2023-02-25 오후 9 09 42" src="https://user-images.githubusercontent.com/48478079/221356117-320ab19d-3f93-4470-84e6-b5b2411eb65f.png">
