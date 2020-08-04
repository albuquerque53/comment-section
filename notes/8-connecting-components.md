# Connecting Components

## Sending data

If we have a component, and this component must send data to other, we can use the 'emit' prop,
basically, this allows us to send a object to other component that will be 'listening' this emit

```
methods: {
  this.$emit('emit-name', {
    prop1: 'data to',
    prop2: 'emit'
  })
}
```

## Receiving data

First, the component who'll send data must be inside of receiver, like

```
  <ComponentWhoSends></ComponentWhoSends>
```

Now, we can set a directive 'on' to listen this emmit and then execute a method

```
  <ComponentWhoSends v-on:emit-name="myMethod"></ComponentWhoSends>
```

And when he (emit) is called, he will send a necessary data to other component
