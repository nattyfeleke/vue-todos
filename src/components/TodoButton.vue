<script setup>

</script>

<template>
    <button>
        <!-- Create is the default text if no child element is passed for the button component or if it is just self closing tag -->
        <slot > Create</slot>
    </button>
</template>



<style lang="scss" scoped>
  button {
    padding: 8px 16px;
    border: none;
  }
</style>