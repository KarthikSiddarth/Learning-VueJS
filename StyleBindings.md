### Binding inline styles

**Object Syntax**

Vue Directive - `v-bind:style`

>Example
```
<div v-bind:class="{color: fcolor, fontSize: fsize}></div>
```

The syntax is familar to CSS but the difference is it should be JavaScript Object and we can use `camelCase or kebab-case` but using `kebab-case`, the key should be encosed with quotes `example: font-size`

Like Style Binding, we can bind style object directly rather than using inline object
>Example

>In HTML
```
<div v-bind:style="styleObject"></div>
```
>In Vue instance
```
data: {
  styleObject: {
    color: 'red',
    'font-size': '50px',
    backgroundColor: 'green'
  }
}
```

Like in class bindings, we can use computed properties and make it to return an object.
>Example
```
data: {
  fcolor: 'red'
  fsize: '50px'
  }
computed: {
  styleObject: function () {
    return {
      color: this.fcolor,
      'font-size': this.fsize,
    }
  }
}
```

**Array Syntax**

Array syntax allows to bind mutiple style objects to the same element
>Example
> In HTML 
```
<div v-bind:style="[fontStyles, bgStyles]"></div>
```
>In Vue instance
```
data: {
  fontStyle: {
    color: 'red',
    'font-size': '50px'
  },
  bgStyles: {
    backgroundColor: 'green'
  }
}
```

**Auto Prefixing**

>*Notes yet to be added*

**Mutiple values**

>*Notes yet to be added*
