<template>
  <h1> {{ msg }}</h1>
  <button @click="add"> Add </button>
  <button @click="remove"> Remove </button>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  // Documentation
  // emits: ['count-add', 'count-remove']
  // Validation
  emits: {
    'count-remove': null,
    'count-add': payload => payload && payload.number && typeof payload.number === "number" ? true : false 
  },
  setup(props, { emit }) {
    function add() {
      emit('count-add', { number: "10" })
    }
    function remove() {
      emit('count-remove')
    }

    return { add, remove }
  }
  
}
</script>