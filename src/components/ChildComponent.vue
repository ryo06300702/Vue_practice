<template>
<div>
  <h2>child component</h2>
  <slot name="head"></slot>
  <slot>default slot</slot>
  <slot name="foot"></slot>
</div>
</template>

<script>
  export default {
    data() {
      return {
        message: '<span>Hello Vue</span>',
      }
    },
  };
</script>