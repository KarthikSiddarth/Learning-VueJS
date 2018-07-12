## Class Binding

### Binding HTML Classes

**Object Syntax**

Using Vue directive `v-bind`, we can toggle classe in an element based on its boolean value

>Example
```
<div v-bind:class="{active: isActive}">{{ name }}</div>
```

In the above example, based on the **truthyness** of the value `isActive`, the class `active` will be added to the element

In this way. we can toggle more than one class

>Example
```
<div v-bind:class="{active: isActive font: makeGreen}">{{ name }}</div> 
```
>In Vue instance
```
data: {
  isActive: true,
  makeGreen: false
}
```
In the above example, the class `active` will be added to the element but not the class `font` because the value of `makeGreen` in the data property is **falsy.**

The bound object doesn't have to be inline, that is, we don't need to define the object at the element instead we can create an object that has all the classes defined in the data property in Vue instance.

>Example

>In HTML
```
<div v-bind:class="classObject">{{ name }}</div>
```

>In Vue Instance
```
data: {
  classObject: {
    active: true,
    font: false,
  }
}
```

**Binding through computed property**

We can also bind `classObject property` through computed property but the condition is the computed property should return an object

>Example

>In HTML
```
<div v-bind:class="classObject">{{ name }}</div>
```

>In Vue Instance
```
data: {
  isActive: true,
  makeGreen: false,
  name: "albert einstein"
},
computed: {
  classObject: function () {
    return {
      active: this.isActive,
      font: this.makeGreen
    }
  }
}
```

### Array Syntax

We can pass an array to `v-bind:class` to apply to a list of classes

>Example

>In HTML
```
<div v-bind:class="[activeClass, fontClass]"></div>
```
>In Vue Instance
```
data: {
  activeClass: active
  fontClass: font
}
```
>This will render
```
<div class="active font"></div>
```

Array syntax provide facility to toggle classes conditionally

>Example
```
<div v-bind:class="[isActive ? activeClass:fontClass]"></div>
```
In the above example, if the `isActive` value is true, the value of the `activeClass` property will be added to the class attribute else the value of `fontClass` property will be added to the class attribute.


It is also possible to use Object syntax in Array syntax
>Example
```
<div v-bind:calss="[{active: isActive}, fontClass]"></div>
