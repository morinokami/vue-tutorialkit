---
type: lesson
title: Event Listeners
focus: /App.vue
---

# Event Listeners

We can listen to DOM events using the `v-on` directive:

```vue-html
<button v-on:click="increment">{{ count }}</button>
```

Due to its frequent use, `v-on` also has a shorthand syntax:

```vue-html
<button @click="increment">{{ count }}</button>
```

Here, `increment` is referencing a function declared in `<script setup>`:

```vue{6-9}
<script setup>
import { ref } from 'vue'

const count = ref(0)

function increment() {
  // update component state
  count.value++
}
</script>
```

Inside the function, we can update the component state by mutating refs.

Event handlers can also use inline expressions, and can simplify common tasks with modifiers. These details are covered in <a target="_blank" href="https://vuejs.org/guide/essentials/event-handling.html">Guide - Event Handling</a>.

Now, try to implement the `increment` function yourself and bind it to the button using `v-on`.
