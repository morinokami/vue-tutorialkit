---
type: lesson
title: Components
focus: /App.vue
---

# Components

So far, we've only been working with a single component. Real Vue applications are typically created with nested components.

A parent component can render another component in its template as a child component. To use a child component, we need to first import it:

```js
import ChildComp from './ChildComp.vue'
```

Then, we can use the component in the template as:

```vue-html
<ChildComp />
```

Now try it yourself - import the child component and render it in the template.
