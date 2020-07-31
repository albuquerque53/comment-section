# Commenting On

We gonna make the comment form works, adding the input to our comment array

## Creating the method

We will create a new propertuy into our component, the methods (key) who will have all methods of this component

```
new Vue({
  el: // render div,
  template: // html,
  data: // comments,
  methods: {
    // here
  }
})
```

The method will be addComment, when the 'comment' button get a click, this method will run

```
methods: {
  addComment() {
    console.log('Working 1 2 3')
  }
}
```

For now, that is what the method will do, just display a message in the console

### On click Directive

The on directive will 'bind' the element for an event, then will do something

```
<t-on:<event>="do someting">
```

In this case we'll use the click event, and we want to run the created method (addComment)

```
<button type="submit" t-on:click="addComment">Comment</button>
```

### Two-Way Data-Binding

#### What It Means?

This means that we can send data for two sides of a application

1. From Model to View
2. From View to Model (For comment on, we will use that)

#### Hands On

We'll insert two items into our data property, the name (will store the author of comment) and message (the content of comment)

```
data() {
  return {
    comments: [
      // Comments
    ],

    name: '',
    message: ''
  }
}
```

The data is ready, now in template we will use a model directive to 'connect' these two properties with the two inputs

```
v-model="data-property-key"
```

Now, when the user insert info into input, automatically, the data will to 'name' & 'message' properties (into de Model layer)

### Adding the comment to comments array

With v-model configured, all input will send to Model Layer, this data can be accessed into the Model with

```
this.name // HTML Input in name
this.message // HTML Input in message
```

Easily, to insert these informations into comments array, we gonna use 'push' into our addComment method

```
methods: {
  addComment() {
    
    this.message.push({
      name: this.name,
      message: this.message
    })

  }
}
```
