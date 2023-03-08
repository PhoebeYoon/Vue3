##### 🌵 Vue3.js


 ### Expressions
 ```
 <div id="app">
  <p>I have a {{ product }}</p>
  <p>{{ product + 's' }}</p>
  <p>{{ isWorking ? 'YES' : 'NO' }}</p>
  <p>{{ product.getSalePrice() }}</p>
</div>
 
 ```
 
 ### Binding
 ```
 <a v-bind:href="url">...</a>
 <a :href="url">...</a>
 
[ fasle / ture 를 속성에 추가 삭제 ]
 <button :disabled="isButtonDisabled">...
 <div :class="{ active: isActive }">...
 <div :style="{ color: activeColor }">

 ```
 
 ## Actions/Events
 ```
 <button v-on:click="addToCart">...
 <button @click="addToCart">...
 <button @click="addToCart(product)">...
 <form @submit.prevent="addProduct">...
 <img @mouseover.once="showImage">...

.stop	Stop all event propagation
.self	Only trigger if event.target is element itself
 
 
 [Keyboard entry example ]
 <input @keyup.enter="submit">
 
 [Call onCopy when control-c is pressed]
 <input @keyup.ctrl.c="onCopy"> 
  
 ```
 
 ## List rendering 
 
 ```
 <li v-for="item in items"
    :key="item.id">
  {{ item }}
</li>

<li v-for="(item, index) in items">...
<li v-for="(value, key) in object">...
<cart-product v-for="item in products"
              :product="item"
              :key="item.id">
 
 ```
 
 ## Directives
 
 ```
 [Element inserted/removed based on truthiness]
 <p v-if="inStock">{{ product }}</p>
 
<p v-else-if="onSale">...</p>
<p v-else>...</p>

[Toggles the display: none CSS property]
<p v-show="showProductDetails">...</p>

[Two-way data binding]
<input v-model="firstName" >
v-model.lazy="..."   (Syncs input after change event)
v-model.number="..."  ( Always returns a number )
v-mo del.trim="..." ( Strips whitespace )
 
 ```

## Component anatomy
```
Vue.component('my-component', {
  components: {
    // 템플릿에서 사용할 수 있는 구성요소
    ProductComponent,
    ReviewComponent  ( 
  },
  props: {
    // 컴포넌트가 허용하는 매개 변수들 및 유형들
    message: String,
    product: Object,
    email: {
      type: String,
      required: true,
      default: "none"
      validator: function (value) {
        // Should return true if value is valid
      }
    }
  },
  data: function() {
    // `data` 함수여야 한다. 그래서 data(){ } 형태로 사용함
    return {
      firstName: 'Vue',
      lastName: 'Mastery'
    }
  },
  computed: {
    //  상태가 변경될때까지 캐시된 값 반환
    fullName: function () {
      return this.firstName + ' ' + this.lastName
    }
  },
  watch: {
    // firstName 값이 변경되면 호출된다
    firstName: function (value, oldValue) { ... }
  },
  methods: { ... },
  template: '<span>{{ message }}</span>',
  // 여러줄일 경우 백틱(`)을 사용할 수도 있다
})
```

## Custom events

```
[Set listener on component, within its parent]
<button-counter v-on:incrementBy="incWithVal">

[Inside parent component]
methods: {
  incWithVal: function (toAdd) { ... }
}

[Inside button-counter template]
this.$emit(
    'incrementBy', // Custom event name
    5 // Data sent up to parent
  )


```
## Slots

```
[ Using a single slot - Component template ]
<div>
  <h2>I'm a title</h2>
  <slot>
    Only displayed if no slot content
  </slot>
</div>

[ Use of component with data for slot ]
<my-component>
  <p>This will go in the slot</p>
</my-component>

```
##  Multiple slots
```
[ Component template ]
<div class="container">
  <header>
    <slot name="header"></slot>
  </header>
  <main>
    <slot>Default content</slot>
  </main>
  <footer>
    <slot name="footer"></slot>
  </footer>
</div>

[ Use of component with data for slots ]
<app-layout>
  <h1 slot="header">Page title</h1>
  <p>the main content.</p>
  <p slot="footer">Contact info</p>
</app-layout>

```





출처 : https://devhints.io/vue
