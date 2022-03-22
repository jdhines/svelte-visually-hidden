# [Demo](https://codesandbox.io/s/svelte-visually-hidden-u4fhqz)
# Accessible Visually Hidden Component
A Svelte component for having accessible screen reader text that's invisible to other users. Useful for explaining parts of a UI that rely on icons or other visual, non-written cues.

Ported from Josh Comeau's [Visually Hidden](https://www.joshwcomeau.com/snippets/react-components/visually-hidden/) component for React.

# Usage
You can copy-paste the code from `VisuallyHidden.svelte` to use in your project. Besides Svelte there's no other dependencies.

```html
  <VisuallyHidden custom-prop="custom">
    Create a new message
  </VisuallyHidden>
```
