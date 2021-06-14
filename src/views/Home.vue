<template>
<div class="home">
  <input type="text" v-model="message" @keyup.enter="addItem">
  <Button label="Add" @click.native="addItem" class="add" />
  <Button label="Delete All" @click.native="deleteAlItems" class="deleteAll" />
  <ul>
    <Item v-for="(todos, index) in todoList" :key="index" :index="index" :todos="todos" :deleteItem="deleteItem" :completedTask="completedTask" />
  </ul>
  <div class="completedContainer">
    <h2>{{ msgCompleted }}</h2>
    <ul class="">
      <CompletedList v-for="(completed, index) in completedList" :key="index" :completed="completed" />
    </ul>
  </div>
</div>
</template>
<script>
import Button from '@/components/Button.vue'
import Item from '@/components/Item.vue'
import CompletedList from '@/components/CompletedList.vue'

export default {
  name: 'home',
  components: {
    Button,
    Item,
    CompletedList
  },
  data() {
    return {
      message: "",
      todoList: [],
      completedList: [],
      msgCompleted: "Completed List"
    }
  },
  methods: {
    addItem() {
      if (this.message.trim().length > 0) {
        this.todoList.push(this.message)
      }
      this.message = "";
    },
    deleteItem(index) {
      this.todoList.splice(index, 1);
    },
    deleteAlItems() {
      this.todoList = [];
      this.message = "";
    },
    completedTask(index, todos) {
      this.todoList.splice(index, 1)
      this.completedList.push(todos)
    }

  }

}
</script>

<style scoped lang="scss">
li {
    list-style: none;
}

.add {
    background-color: white;
    border: 1px solid #444444;
}

.deleteAll {
    background-color: white;
    border: 1px solid #ff0000;
}

.completedContainer{
  display: inline-block;
}
</style>
