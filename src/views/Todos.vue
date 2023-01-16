<template>
    <div>
        <h2 class="app__title">To do List</h2>
        <todo-input @add="addNewTodo"/>
        <hr class="app__hr">
        <div class="app__container">
            <todo-list :list="uncompletedUp" @remove="removeTodo"/>
            <p v-if="!todos.length">список пуст</p>
        </div>

    </div>
</template>

<script>
import TodoList from "@/components/TodoList";
import TodoInput from "@/components/TodoInput";

export default {
    name: 'App',
    components: {
        TodoInput,
        TodoList
    },
    data: () => ({
        todos: [
            {
                id: 1,
                title: 'Купить хлеб',
                completed: false
            },
            {
                id: 2,
                title: 'Купить масло',
                completed: false
            },
            {
                id: 3,
                title: 'Купить молоко',
                completed: false
            }
        ]
    }),
    computed: {
        uncompletedUp(){
            return this.todos.sort((a,b) => a.completed - b.completed)
        }
    },
    methods: {
        removeTodo(id){
            this.todos = this.todos.filter(x => x.id !== id)
        },
        addNewTodo(item){
            this.todos.push({
                title: item,
                id: Date.now(),
                completed: false
            })
            console.log(this.todos.sort((a,b) => a.completed - b.completed))
        }
    }
}
</script>

<style scoped>

</style>