---
type: lesson
title: Lifecycle and Template Refs
focus: /App.vue
---

# Lifecycle and Template Refs

So far, Vue has been handling all the DOM updates for us, thanks to reactivity and declarative rendering. However, inevitably there will be cases where we need to manually work with the DOM.

We can request a **template ref** - i.e. a reference to an element in the template - using the <a target="_blank" href="https://vuejs.org/api/built-in-special-attributes.html#ref">special `ref` attribute</a>:

```vue-html
<p ref="pElementRef">hello</p>
```

<div class="composition-api">

To access the ref, we need to declare a ref with matching name:

```js
const pElementRef = ref(null)
```

Notice the ref is initialized with `null` value. This is because the element doesn't exist yet when `<script setup>` is executed. The template ref is only accessible after the component is **mounted**.

To run code after mount, we can use the `onMounted()` function:

```js
import { onMounted } from 'vue'

onMounted(() => {
  // component is now mounted.
})
```

This is called a **lifecycle hook** - it allows us to register a callback to be called at certain times of the component's lifecycle. There are other hooks such as `onUpdated` and `onUnmounted`. Check out the <a target="_blank" href="https://vuejs.org/guide/essentials/lifecycle.html#lifecycle-diagram">Lifecycle Diagram</a> for more details.

Now, try to add an `onMounted` hook, access the `<p>` via `pElementRef.value`, and perform some direct DOM operations on it (e.g. changing its `textContent`).
