---
description: >-
  Components are isolated sets of logic (Javascript), visualization (JSX/HTML)
  and possible styling (CSS).
---

# Components

There are two types of components, **Class components** and **Function components**.

{% hint style="info" %}
In React 16.8 was added the Hooks and now it is **recommended to use the Function components along with Hooks**.

The component's name MUST **start with an upper case letter**.
{% endhint %}

### Class Component

A class component must include the extends React.component statement.

```jsx
class Dog extends React.Component {
    render () {
        return <h2>Hi, I am a Dog</h2>;
    }
}
```

### Function Component

A function component also returns HTML.\
Here is the same example above, but much more simple for write and understand.

```jsx
function Dog() {
    return <h2>Hi, I am a Dog</h2>;
}
```
