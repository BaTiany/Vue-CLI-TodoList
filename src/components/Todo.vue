<template>
  <div class="todo">
    <input
      v-model="inputVal"
      type="text"
      placeholder="请输入内容..."
      />
    <button @click="addTodo">Add</button>

    <ul>
      <TodoItem
        v-for="(item,index) in todos"
        :key="index"
        :todo="item"
        :index="index"
        @abc="delTodo"
       />
    </ul>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
  data () {
    return {
      inputVal:'',
      todos:[
        '吃饭',
        '睡觉',
        '打豆豆'
      ]
    }
  },

  components: {
    TodoItem
  },

  methods: {
    addTodo () {
      this.todos.push(this.inputVal);
    },

    delTodo (index) {
      this.todos.splice(index,1)
    }
  }
}
</script>

<style lang="scss">

</style>

