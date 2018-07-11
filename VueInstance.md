### The Vue Instance


##### To create a Vue instance
```
const app = new Vue({
  //options
})
```
An options object must be passed to the constructor when creating a new Vue instance.

A typical Vue application consist a **root Vue instance** and the instance will have resuable **components** organized one by one or nested.

Components are also Vue instances which take options objects when creating.

#### Properties and Methods

When the Vue instance is created, the instance provide number of properties and methods, mostly used ones are data, el, method and so on
These are perfixed with \$ dollar sign

#### Date object

The properties in the Data object is added to the Vue's reactivity system when the instance in which the corresponing data object present is created.

When the value of any if the property changes the corresponding content reference in the DOM will render the changed value.

##### Example
```
const app = new Vue({
  el: '#app'
  data: {
    a: 1
  }
})
```
If the any of the value of property changes in the data object, the changes will get renders.

> **Note:** Changes to the properties in the data object will only get rendered when those properties existed when creating the instance.
> For Example: app.b = "hello", this will not get rendered or added to the data object of the instance.
> Also when the data object is made to be frozen using Object.freeze() method, the value of the properties can't be changed.

#### Instance Life Cycle Hooks:
Life cycle hooks provided opportunity to users to add their own code at specific stages of the instance.

Life cycle hooks of an instance are
1. Created
2. Mounted
3. Updated
4. Destroyed

All LifeCyle hooks are called with their **this** context of the Vue instance.

Example of using Life cycle hook

```
const app = new Vue({
  el: '#app'
  data: {
    message: 'hello, world'
  }
  created: function () {
    console.log(`message is ${this.message})
  }
})
```
**DO NOT USE `ARROW FUNCTIONS` ON A PROPERTY OR CALLBACK INSIDE THE VUE INSTANCE. SINCE `ARROW FUNCTIONS` ARE BOUND TO PARENT CONTENT, `this` WILL NOT REFER THE VUE INSTANCE.**
