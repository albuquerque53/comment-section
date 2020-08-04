<template>
  <div class="container">
    <h1>Comments</h1>
    <hr>
    <FormTodo v-on:add-todo="addComment"></FormTodo>
    <div class="list-group-item" v-for="comment in allComments" v-bind:key="comment.id">
      <span class="comment__author">
        Author: <strong>{{ comment.name }}</strong>
      </span>
      <p>{{ comment.message }}</p>
      <div>
        <a href="#" title="Delete" v-on:click.prevent="removeComment(comment.id)">
          Delete
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import FormTodo from './FormTodo'

export default {
  components: {
    FormTodo
  },
  data() {
    return {
      comments: [],
    }
  },
  methods: {
    addComment(comment) {
      this.comments.push(comment)
    },
    removeComment(index) {
      this.comments.splice(index, 1);
    }
  },
  computed: {
    allComments() {
      return this.comments.map(comment => ({
        ...comment,
        name: comment.name.trim() === '' ? 'Anonymous' : comment.name
      }))
    }
  },
  watch: {
    comments(val) {
      console.log('Changed/Created a Comment', val)
    }
  }
}
</script>
