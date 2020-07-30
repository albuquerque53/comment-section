# In Pratice (View Layer)

## Implementation

The basic way to implement VueJS to an application is by CDN provided [here](https://vuejs.org/v2/guide/#Getting-Started)

1. You need create a new component with:

```
<script src="vueCDN"></script>

<script>
    new Vue()
</script>
```

> The Vue instance will receive a object with informations about your component

2. Create a div (in html), this div will be used to render a template

```
<body>
    <div id="app"></div>
</body>
```

3. Now, you can specify the div in the Vue Component with 'el' key

```
<script>
    new Vue({
      'el': '#app'
    })
</script>
```

4. After that, will need a html to render in that div, this html will be a template of your component

```
<script>
    new Vue({
      'el': '#app',
      'template': `
        <h1>Hello, VueJS!</h1>
      `
    })
</script>
```

## Conclusion

This is a Basic way to intance a VueJS component into a application
