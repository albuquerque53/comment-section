# Model Layer

## Instance

Into the VueJS component, after template, will have a 'data' property, and the value will be a callback function

```
// same as:  data: function() {}
data() {
    
}
```

### Set up of Data method

The metod will return a object, this object must have the properterties of component

```
data() {
  return {
        
  }
}
```

We are building a comment system, the returned object will have an array with the comment info (name and message)

```
data() {
  return {
    comments: [
      {
        name: 'UserName',
        message: 'The Users message'
      }
    ]
  }
}
```

### Using data properties (Model) into template (View)

For HTML VueJS offers the 'v-for' attribute for tags, this attribute is like a 'for' loop of JS

> The return of data property are already 'sub-loaded' in template, so that we can use them (ViewModel)

```
<div class="list-group-item" v-for="comment in comments">
  <p>{{ comment.message }}</p>
</div>
```

#### Basically...

1. We used a a for loop to run throught the array comments with 'v-loop' [Directive](https://vuejs.org/v2/guide/syntax.html#Directives). 
2. For each comment, we create a paragraph with the respective content.
3. We used {{ }} to insert JS data into HTML, this technique is called [Interpolation](https://vuejs.org/v2/guide/syntax.html#Interpolations).
