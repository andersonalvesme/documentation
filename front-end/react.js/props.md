# Props

Props are arguments passed into React components via HTML attributes:

```jsx
// Passing as a string
const myElement = <Car brand="Ford" />;

// Passing as a variable
const carName = "Ford";
const myElement = <Car brand={ carName } />;

// Passing as a object
const carInfo = { name: "Ford", model: "Mustang" };
const myElement = <Car brand={ carInfo } />;
```

The component receives the argument as a `props` object:

```jsx
function Car(props) {
  // String and as a variable
  return <h2>I am a { props.brand }!</h2>;

  // As a object
  return <h2>I am a { props.brand.model }!</h2>;
}
```

{% hint style="info" %}
**Note:** React Props are read-only! You will get an error if you try to change their value.
{% endhint %}
