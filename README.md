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
