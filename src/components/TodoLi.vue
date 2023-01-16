<template>
    <li class="item" :class="{ 'item--done' : todo.completed }">
        <span class="item__title">
            <input type="checkbox" class="item__input" @click="todo.completed = !todo.completed" :checked="todo.completed">
            {{ todo.title }}
        </span>
        <button class="item__remove" @click="$emit('remove', todo.id)">
            &times;
        </button>
    </li>
</template>

<script>
export default {
    name: "TodoLi",
    props: {
        todo: {
            type: Object,
            default: () => ({}),
            required: true
        }
    }
}
</script>

<style scoped lang="sass">
.item
    border: 1px solid #ccc
    display: flex
    justify-content: space-between
    align-items: center
    padding: 1.5rem 2rem
    margin-bottom: 1rem
    border-radius: 15px
    font-size: 24px

    &--done
        & .item__title
            text-decoration: line-through

    &__remove
        background: #ff5500
        border-radius: 50%
        color: white
        font-size: 20px
        border: none
        cursor: pointer

    &__input
        margin-right: 1rem

</style>