:cactus: Vue3 Lesson 
## v-if 디렉티브에 대해 알아보자. 
조건에 따라 내용을 표시하거나 표시하지 않거나 합니다.

```
<p v-if="조건"> 조건이 ture 일때 표시하는 내용 </p>
<p v-else > 조건이 false 일때 표시하는 내용 </p>
```

```
<p v-if="조건1"> 조건1이 ture 일때 표시하는 내용 </p>
<p v-else-if="조건2"> 조건1이 false 이고, 조건2가 ture 일때 표시하는 내용 </p>
<p v-else > 우의 2개의 조건이 false일대 표시하는 내용 </p>
```
