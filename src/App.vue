<template>
  <!-- Don't drop "q-app" class -->
  <div id="q-app">
    <q-layout ref="layout" view="hHr LpR lFf">

      <q-toolbar slot="header">
        <q-toolbar-title>Quasar Todo App
          <span slot="subtitle">By Nathan Gaul</span>
        </q-Toolbar-title>

      </q-toolbar>

      <div id="page">
        <new-todo-input @newTodo="newTodo" />
        <todo-list :todos="todos" @deleteTodo="deleteTodo"/>
      </div>

    </q-layout>
  </div>
</template>

<script>
/*
 * Root component
 */
import {
  QLayout,
  QToolbar,
  QToolbarTitle
} from 'quasar'

import NewTodoInput from './components/NewTodoInput'
import TodoList from './components/TodoList'

let nextId = 0

export default {
  data () {
    return {
      todos: [
        {
          title: 'Get shit done',
          id: nextId++
        }
      ]
    }
  },
  methods: {
    newTodo (title) {
      this.todos.push({
        title: title,
        id: nextId++
      })
    },
    deleteTodo (id) {
      this.todos = this.todos.filter(todo => todo.id !== id)
    }
  },
  components: {
    QLayout,
    QToolbar,
    QToolbarTitle,
    NewTodoInput,
    TodoList
  }
}
</script>

<style lang="stylus">
#page
  width: 60%
  margin 0 auto
</style>

