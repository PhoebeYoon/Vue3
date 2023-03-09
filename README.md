##### 🌵 Vue3.js


## v-text
```
<body>
    <div id="app">
        <p>{{ gretting }}</p>
        <p> Is it true:{{ isItTrue ? 'Yes':'No' }}</p>
        <p>{{ array[0] }}</p>
        <p>{{ obj.car }}</p>
        <p>{{ func() }}</p>
    </div>
</body>

data(){
            return {
                gretting:'Hello guys today is ' + date,
                isItTrue: true,
                array:['Francis','Jane'],
                obj:{
                    car:'Ferrari'
                },
                func:()=>{
                    return 'Message from function'
                }
            }
        }
````

