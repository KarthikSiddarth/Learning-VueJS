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

#### Date object

The properties in the Data object is added to the Vue's reactivity system when the instance in which the corresponing data object present is created.

When the value of any if the property changes the corresponding content reference in the DOM will render the changed value.

##### Example
```
const app = new Vue({
  data: {
    a: 1
  }
})
```
If the any of the value of property changes in the data object, the changes will get renders.

> **Note:** Changes to the properties in the data object will only get rendered when those properties existed when creating the instance.
> For Example: app.b = "hello", this will not get rendered or added to the data object of the instance.
> Also when the data object is made to be frozen using Object.freeze() method, the value of the properties can't be changed.
