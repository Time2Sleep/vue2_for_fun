<template>
    <div>
        <ul class="list">
            <transition-group name="flip-list">
                <template v-for="item in list">
                    <todo-li :todo="item" @remove="removeTodo" :key="item.id"/>
                </template>
            </transition-group>
        </ul>
    </div>
</template>

<script>
import TodoLi from "@/components/TodoLi";
export default {
    name: "TodoList",
    components: {TodoLi},
    props: {
        list: {
            type: Array,
            default: () => ([])
        }
    },
    methods: {
        removeTodo(id){
            this.$emit('remove', id)
        }
    }
}
</script>

<style scoped lang="sass">
.list
    list-style: none
    margin: 0
    padding: 0

.flip-list-move
    transition: transform 1s

</style>