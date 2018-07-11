### Template Syntax
  VueJs uses HTML based template syntax that allows to declaratively bind the rendered DOM with underlying Vue instance's Data object.

##### Text

\<p\>{{ message }}\<\/p\>

The brackets inside the `<p></p>` tag are called **mustache syntax**, when the instance is created, the text that the *message* key that points to will get rendered.

Using `v-once` directive, you can set the DOM to not to render the data more than once. so if the data gets changed, the changed content will not get rendered.

##### Raw HTML

To interpret the declared data as HTML not plain text, v-html directive should be used.

>Example:

>data: { rawHtml: '\<span style="color: red;"\>some message\<span\>' }

>\<p\>using mustaches: {{ rawHtml }} \<p\>

>\<p\>using v-html directive : \<span v-html="message"\>\<span\>\<\/p\>

In the first `p` tag, the text will be rendered as it is but in second one the text will be interpreted, style will get applied and will display the text content only and the `span' tag will get attached to DOM.

##### Attributes

Using v-bind directive, we can bind the data from the Vue instance to the HTML attribute
>Example

> In the Vue Instance
```
data: { idText: "someIDName"}
```
>In the HTML file
```
<p v-bind:id="idText"></p>
```

##### Using JavaScript Expression

In VueJS, you can using JavaScript expressions for data binding

>Example

>{{ message[0] }}

>{{ "hello" + message }}

> {{ true ? message1 : message2

>```<div v-bind:id="idName + '1'"></div>```

**Restriction:** Each binding can only contain **one single expression**

Below syntax will not work

> {{ var a = 1 }}

> {{ if(true) { return message } }}

because the above two syntax are statements not expressions and for conditions use ternery expression.

Global objects that shipped with engine will work line `Math` and `Date` but attempting use user defined global objects are not recommended

##### Directives
