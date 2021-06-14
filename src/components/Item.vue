<template>
  <li class="">
    {{ todos }}
    <Button label="Delete" @click.native="deleteItem(index)" class="delete" />
    <Button label="Completed" @click.native="completedTask(index, todos)" class="completed"/>
  </li>
</template>

<script>
import Button from '@/components/Button.vue'

export default {
  name: 'Item',
  props: ['todos', 'deleteItem','completedTask', 'index'],
  components: {
    Button
  }
}
</script>

<style scoped lang="scss">
    .delete{
      width: 100px;
      background-color: white;
      border: 1px solid  #ff3c3c;

      &:hover{
        color: white;
        background-color: #ff3c3c;
      }
    }

  .completed{
    background-color: white;
    border: 1px solid  #5ca24f;
    width: 100px;
    
    &:hover{

      color: white;
      background-color: #5ca24f;
    }
  }
</style>
