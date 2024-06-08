---
type: lesson
title: Props
focus: /App.vue
---

# Props

A child component can accept input from the parent via **props**. First, it needs to declare the props it accepts:

```vue
<!-- ChildComp.vue -->
<script setup>
const props = defineProps({
  msg: String
})
</script>
```

Note `defineProps()` is a compile-time macro and doesn't need to be imported. Once declared, the `msg` prop can be used in the child component's template. It can also be accessed in JavaScript via the returned object of `defineProps()`.

The parent can pass the prop to the child just like attributes. To pass a dynamic value, we can also use the `v-bind` syntax:

```vue-html
<ChildComp :msg="greeting" />
```

Now try it yourself in the editor.
