### Computed properties

Computed properties are properties in the Vue instance that typically has functions and when its is called, it computes a value using values in the instances and values passed to it, the computed is then rendered in the DOM.

**Basic Example**

> In HTML
```
<div id="app">
  <p>Original Message {{ message }}</p>
  <p>Computed reverse message {{ reverseMessage }}</p>
</div>
```

> In Vue Instance
```
const app = new Vue({
  el: '#app'
  data: {
    message: 'Hello, World'
  },
  computer: {
    reverseMessage: function () {
      this.message.split('').reverse().join('')
    }
  }
})
```
> Rendered Text
```
Hello, World
dlroW ,olleH
```

**Note:** When the content of the **message** property changed, the reversed version that changed message will be rendered in the template where it is referred.

**Computed Caching vs Methods**

The same action of reversing text can also be achived by using methods by defining a function in the method object in Vue instance.

>Example
```
<p>Reversed Message {{ reverseMessage() }}</p>

method: function reverseMessage () {
  this.message.split('').reverse().join('')
}
```
Using Computed properties and methods will provide same result but in Computed properties are cached based on their dependencies.

A computed property will only compute value when its dependencies get changed so whenever the computed property is refered, it will return the already computed value, whereas in methods, whenever its called, the value is computed each time, this increase computation and is expensive.

>Example
```
computed: {
  now: function (){
    return Date.now()
  }
}
```
In above example, whenever the `now` is referenced, it will return the already computed value and it won't change because it does not depend on any other values.


**Computed Setter**

Computed properties can also be used to set values to properties but by default computed properties are getter

So when a computed properties changes, the properties that computed property is depend upon can be changed using computed properties setter property.

>Example

>In HTML
```
<div id="app">
  <p>{{ fullname }}</p>
</div>
```
>In Vue Instance
```
const app = new Vue({
  el: '#app',
  data: {
    firstname: "albert"
    secondname: "einstein"
  },
  computed: {
    fullname: {
      get: function () {
        return `${this.firstname} ${this.lastname}`
      },
      set: function (val) {
        val = val.split(' ')
        this.firstname = val[0]
        this.lastname = val[val.length-1]
      }
    }
  }
})
```

The above example will set first name and last name property to new value if the user provide a new value to fullname property `app.fullname = "nikola tesla"`
