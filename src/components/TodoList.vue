<template>
  <div>
    <q-card v-for="todo in todos" :key="todo.id">
      <q-card-title>
          {{ todo.title }}
          <div slot="right"><q-btn flat @click="deleteTodo(todo)"><q-icon name="delete" color="secondary"/></q-btn></div>
      </q-card-title>
    </q-card>
  </div>
</template>

<script>
import {
  QCard,
  QCardTitle,
  QBtn,
  QIcon
} from 'quasar'

export default {
  data () {
    return {}
  },
  props: ['todos'],
  methods: {
    deleteTodo (todo) {
      this.$emit('deleteTodo', todo.id)
    }
  },
  components: {
    QCard,
    QCardTitle,
    QBtn,
    QIcon
  }
}
</script>

<style>
</style>
