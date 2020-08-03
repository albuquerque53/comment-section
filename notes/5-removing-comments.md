# Removing Comments

## The method

First, we'll need set the 'v-on' directive, with 'click' argument into 'delete' button:

```
<a href="#" v-on:click"<ourDeleteMethod>">Delete Comment</a>
```

This directive will call the removeComment method, let's create this function inside the 'methods' property in our component

```
methods: {
  addComment(),

  removeComment() {}
}
```

This method need identify wich of comment we want to destroy, for that, 
in our 'loop' directive in comments, we will require the 'index' for each comment

```
<div v-for="(comment, index) in comments">
  <p>{{ name }}</p>
  <p>{{ message }}</p>

  <a href="#" v-on:click"<ourDeleteMethod>">Delete Comment</a>
</div>
```

Let's identify the comment using the index as a parameter to removeComment method

```
<a href="#" v-on:click"removeComment(index)">Delete Comment</a>
```

Let's receive the index in method

```
removeComment(index) {
  console.log(index)
}
```

Now, we'll use the splice method in comments array to remove the item with index = to parameter

```
removeComment(index) {
  this.comments.splice(index, 1)
}
```

Is working! But every we clicks the button, we go to top of page (because the a is a anchor, refering to '#', namely, the top of page)
To stop this behavior, we usually use the 'prevent default' but we can use a [Event Modifier](https://vuejs.org/v2/guide/events.html#Event-Modifiers) for that.
Simply adding '.prevent' in our click directive, we gonna use the 'event.preventDefault()' equivalent

```
<a href="#" v-on:click.prevent"removeComment(index)">Delete Comment</a>
```
