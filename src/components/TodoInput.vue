<template>
    <div class="add app__container">
        <input class="add__input"
               type="text"
               v-model="text"
               placeholder="Добавить новый элемент"
        >
        <button class="add__button" @click="addNew">Добавить</button>
    </div>
</template>

<script>
export default {
    name: "TodoInput",
    data: () => ({
        text: ''
    }),
    methods: {
        addNew(){
            if(!this.text.trim()) return
            this.$emit('add', this.text)
            this.title = ''
        }
    }
}
</script>

<style scoped lang="sass">
.add
    display: flex
    align-items: center
    justify-content: space-between
    &__input
        padding: 1rem
        border-radius: 15px
        border: 1px solid #ccc
        width: 600px
        font-size: 20px

    &__button
        width: 150px
        height: 100%
        padding: 1rem
        border-radius: 15px
        border: 1px solid #ccc
        background: #a5ec5f
        font-size: 20px
</style>