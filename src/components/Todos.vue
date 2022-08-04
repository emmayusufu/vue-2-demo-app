<template>
<div>
    <div v-bind:key="todo.id" v-for="todo in todos">
        <TodoItem v-bind:todo="todo" v-on:del-todo="deleteTodo"/>
    </div>
</div>

</template>

<script>
import TodoItem from './TodoItem.vue'
export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Todos',
    props: {
        todos: Array,
    },
    components:{
    TodoItem,
},
    methods: {
        deleteTodo(id) {
            // eslint-disable-next-line vue/no-mutating-props
            this.todos = this.todos.filter(todo => todo.id !== id)
        }
    }
}

</script>