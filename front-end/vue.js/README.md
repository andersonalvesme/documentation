---
description: The Progressive JavaScript Framework
---

# Vue.js

{% embed url="https://v3.vuejs.org/" %}

Vue (pronounced /vjuː/, like **view**) is a JavaScript framework for building user interfaces.

Simple example:

{% code title="js" %}
```javascript
import { createApp } from 'vue'

createApp({
  data() {
    return {
      count: 0
    }
  }
}).mount('#app')
```
{% endcode %}

{% code title="template" %}
```html
<div id="app">
  <button @click="count++">
    Count is: {{ count }}
  </button>
</div>
```
{% endcode %}

### Single-File Components

Vue components using an HTML-like file format called **Single-File Component** (also known as `*.vue` files, abbreviated as **SFC**).

A Vue SFC, as the name suggests, encapsulates the component's logic (**JavaScript**), template (**HTML**), and styles (**CSS**) in a **single file**.

Here's the previous example, written in SFC format:

```html
<script>
export default {
  data() {
    return {
      count: 0
    }
  }
}
</script>

<template>
  <button @click="count++">Count is: {{ count }}</button>
</template>

<style scoped>
button {
  font-weight: bold;
}
</style>
```

### Options API

TODO

### Composition API

TODO



* anotação dupla chaves (Must stash?)
* Declarative rendering
* Tudo é reativo
* Para setar valor dinamico nas propriedades do html, tem que usar **:**
* style binding
* modificadores, exemplo: stopPropagation
* uso de **template**&#x20;
* keyword **this**&#x20;
* Form Input Bindings
* Two-way Data Binding
