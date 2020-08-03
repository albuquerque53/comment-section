# Anonymous Comment

A comment will be anonymous when the author don't specify his name

## Computed

The computed will be a property of our Component, he's in charge of logic bussiness in View layer

In this case, when a author don't specify the name, her name will be displayes as 'Anonymous', but you real name must be '' (only for View, the name will be 'Anonymous')

### Method allComments

Lets create the computed property and allComments method

```
new Vue({
  el: '#app',
  template: `html`,
  data() {},
  methods: 'method',

  computed: {
    allComments() {}
  }
})
```

The allComments will run through 'comments' array and, if name prop is equal to '', the name will be returned/displayed as 'Anonymous'

```
allComments() {
  return this.comments.map(comment => ({
    ...comment,
    name: comment.name.trim() === '' ? 'Anonymous' : comment.name
  }))
}
```

Now, whe need to use this returned array in for directive on template

```
<div v-for="(comment, index) in allComments">
  <p>{{ name }}</p>
  <p>{{ message }}</p>

  <a href="#" v-on:click"<ourDeleteMethod>">Delete Comment</a>
</div>
```

Basically, we create a bussiness rule, in computed property, separated from View Layer
