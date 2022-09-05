<template>
  <div class="badass-todo">
    <div class="title has-text-centered">Badass Todo</div>

    <form @submit.prevent="addTodo">
      <div class="field is-grouped mb-5">
        <div class="control is-expanded">
          <input v-model="newTodoContent" class="input" type="text" placeholder="Add a todo" />
        </div>
        <div class="control">
          <button :disabled="!newTodoContent" class="button is-info">
            Add
          </button>
        </div>
      </div>
    </form>

    <div v-for="todo in todos" class="card mb-5">
      <div class="card-content">
        <div class="content">
          <div class="columns is-mobile is-vcentered">
            <div class="column">{{ todo.content }}</div>
            <div class="column is-5">
              <button class="button is-light">&check;</button>
              <button class="button is-danger ml-2">&cross;</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script lang="ts">
import { defineComponent } from 'vue'
import { v4 as uuidv4 } from 'uuid'

// export interface Todo {
//   id: string,
//   content: string,
//   done: boolean
// }

export default defineComponent({
  // setup() {
  //   const store = useStore();
  //   // do stuff

  //   return {
  //     store,
  //   }
  // },
  components: {},
  props: {
    name: String,
    msg: { type: String, required: true }
  },
  data() {
    return {
      newTodoContent: '',
      // todos: Todo[],
      // todo: Todo,
    }
  },
  created() { },
  mounted() { },
  methods: {
    addTodo() {
      const newTodo: Todo = {
        id: uuidv4(),
        content: this.newTodoContent,
        done: false,
      }
      // this.todo = newTodo
      // console.log('newTodo', typeof(newTodo))
      // this.todos.push(newTodo)
    },
    newTodoContent() {
      return 'yoyo'
    }
  }

})
</script>


<style>
@import "bulma/css/bulma.min.css";

.badass-todo {
  max-width: 400px;
  padding: 20px;
  margin: 0 auto;
}
</style>
