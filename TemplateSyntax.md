### Template Syntax
  VueJs uses HTML based template syntax that allows to declaratively bind the rendered DOM with underlying Vue instance's Data object.

##### Text

\<p\>{{ message }}\<\/p\>

The brackets inside the `<p></p>` tag are called **mustache syntax**, when the instance is created, the text that the *message* key that points to will get rendered.

Using `v-once` directive, you can set the DOM to not to render the data more than once. so if the data gets changed, the changed content will not get rendered.

##### Raw HTML


