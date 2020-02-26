<template>
  <div id="app" class="small-container">
    <h1>To-Do-List</h1>
    <list-form @add:item="addItem"/>
    <to-do-list />
    <to-do-list :list = ToDoList />
  </div>
</template>

<script>
import ToDoList from '@/components/ToDoList.vue'
import ListForm from '@/components/ListForm.vue'

export default {
  name: 'App',
  components: {
    ToDoList,
    ListForm,
  },
  data(){
    return {
      ToDoList: [
        {
          id: 1,
          status: true,
          item: 'study vue',
        },
        {
          id: 2,
          status: false,
          item: 'study react',
        },
        {
          id: 3,
          status: true,
          item: 'study javascript',
        },
      ],
    }
  },
  methods:{
    addItem(item) {
  const lastId =
    this.ToDoList.length > 0
      ? this.ToDoList[this.ToDoList.length - 1].id
      : 0;
  const id = lastId + 1;
  const newItem = { ...item, id };

  this.ToDoList = [...this.ToDoList, newItem];
}
  }
}
</script>

<style>
button {
    background: #009435;
    border: 1px solid #009435;
  }

  .small-container {
    max-width: 680px;
  }
</style>
