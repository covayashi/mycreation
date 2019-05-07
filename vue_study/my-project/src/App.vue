<template>
  <div class="todo-list">
    <div>
      <ul>
        <todo-item v-for="todo in todos" v-bind="todo" />
      </ul>
    </div>
    <form v-on:submit.prevent="onSubmit">
      <textarea v-model="text"/>
      <input type="submit" value="TODO追加"/>
    </form>
  </div>
</template>

<script>
    import TodoItem from  './components/murayamaheader'

    export default {
        name: 'TodoList',
        components: {
            'todo-item': TodoItem
        },
        data () {
            return {
                text: '',
                todos: []
            }
        },
        methods: {
            onSubmit () {
                this.todos.push({
                    text: this.text
                });
                this.text = ''
            }
        }
    }
</script>

<style scoped>
  .todo-list {
    text-align: left;
  }
</style>