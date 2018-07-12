## Conditional Rendering

Vue Directives for Conditional rendering are 
```
*v-if
*v-else
*v-else-if
*v-show
```
**v-if**

[CodePen - `v-if`](https://codepen.io/devsid/pen/pZJJpm)

To render an element based on some comditon, we can use `v-if`
>Example

> In HTML
```
<p v-if='ok'>Hello, World</p>
<p v-if='ok2'>Bye, See ya</p>
```

> In Vue Instance
```
data: {
  ok: true // truthy
  ok2: false  // falsy
}
```

The value of the binding should be **truthy**, it doesn't have to be boolean and if the value is **falsy** then the element will not be rendered 

In the above example, the first `p` element will be rendered but the second one will not be rendered. 

**v-if and v-else**

[CodePen - `v-if, v-else`](https://codepen.io/devsid/pen/qydZWd?editors=1011)

With `v-else`, we can add else condition to perform conditional rendering

>Example

>In Html
```
<p v-if="ok">{{ message1 }}</p>
<p v-else>{{ message2 }}</p>
```
>In Vue instance
```
date: {
  message1: "Hello"
  message2: "bye"
  ok: true // truthy value
}
```

In the above example if the value of "ok" property is truthy, then the corresponing element or block of elements will be rendered, if it is falsy, then the element which has `v-else` directive will be rendered.

**Note:** The element with the `v-else` directive should be right below the element with `v-if` directive, only then the either of one will be rendered based on the condition.

`v-if and v-else` block can also be used to render block of elements

[CodePen - Rendering group of elements using if, else block](https://codepen.io/devsid/pen/djoMVv?editors=1011)

**v-else-if**

The element with `v-else-if` directive will get rendered when the condition at the `v-if` directive is falsy

Like `v-else`, `v-else-if` should also be placed right below the element that has directive `v-if`

[CodePen - `v-if, v-else-if, v-else`](https://codepen.io/devsid/pen/MBwyzW?editors=1011)
