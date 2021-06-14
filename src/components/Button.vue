<template>
  <button type="button" name="button">{{ label }}</button>
</template>

<script>
export default {
  name: 'Button',
  props: ['label']
}
</script>

<style scoped lang="scss">
  button{
    cursor: pointer;
    border-radius: 5%;
    width: 100px;
    height: 50px;
    border: 0;
    margin: 20px;
  }
</style>
