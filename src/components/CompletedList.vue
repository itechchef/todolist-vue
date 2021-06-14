<template>
  <li>{{ completed }}</li>
</template>

<script>
export default {
  name: 'CompletedList',
  props: ['completed']
}
</script>

<style scoped lang="scss">
  button{
    border: 2px solid green;
    padding: 30px;
  }
</style>
