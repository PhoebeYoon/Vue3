##### 🌵 Vue3.js


## methods에 대해 알아보겠습니다.  

``` html
<div id="app"> 
    <p>{{ welcome()}}</p>
</div>

<script>
// let greeting = ()=>{
//   console.log('outside of greeting')
// }
//  아래것을 주석처리하고 위의 것을 실행, 위의 것을 주석처리하고 아래것을 실행해 보세요
// let greeting ='Nice to see'

const App = {
data(){
  return {
   greeting:'Hello guys! Good to have you here'
  }
},
methods:{
  welcome(){
    return greeting
  }
 }
}
Vue.createApp(App).mount('#app')
</script>
```  
위의 예제에서 알아야 할 것은 methods 에 정의된 greeting를 어디에서 찾느냐이다. 우리가 생각하는 스코프에서가 아니라 App 밖에서 greeting 를 찾는다는 것이다. 위의 2개를 모두 주석처리하면 화면에는 아무것도 나오지 않는다   
그래서 data에 선언된 것을 가져와서 사용하라는 의미로 앞에 this을 붙여준다.   
이제 ``` return this.greeting  ``` 으로 바꿔 실행해보자. 그럼 제대로된 결과가 나온다.








``` html
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <meta http-equiv="X-UA-Compatible" content="ie=edge">
   <script src="https://unpkg.com/vue@next"></script>

   <title>Document</title>
</head>
<body>
    <div id="app">
        <p>{{ welcome() }}</p>
    </div>
</body>
<script>
    const date = new Date().toLocaleString()
    const App = {
        data(){
            return {
                gretting:'Hello guys today is ' + date,
                isItTrue: false,
                array:['Francis','Jane','Steve'],
                obj:{
                    car:'Ferrari'
                },
                func:()=>{
                    return 'Message from function'
                }
            }
        },
        methods:{
            welcome(){
                const randomName = this.array[Math.floor(Math.random() * this.array.length)]
                if(this.isItTrue){
                    return `${this.gretting}, my name is ${randomName}`
                }

                return this.obj.car
            }
        }
    }

    Vue.createApp(App).mount('#app')

</script>
</html>
```

