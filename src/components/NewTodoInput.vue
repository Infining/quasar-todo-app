<template>
  <div>
    <q-input type="text" v-model="title" @keydown.enter="newTodo" placeholder="Add your todos"/>
  </div>
</template>

<script>
import {
  QCard,
  QCardTitle,
  QInput
} from 'quasar'

export default {
  data () {
    return {
      title: ''
    }
  },
  methods: {
    newTodo () {
      if (this.title.length) {
        this.$emit('newTodo', this.title)
        this.title = ''
      }
    }
  },
  components: {
    QCard,
    QCardTitle,
    QInput
  }
}
</script>

<style lang="stylus">
</style>
