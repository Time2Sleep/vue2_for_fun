<template>
    <div id="app" class="app">
        <main-header :routes="routes"/>
        <router-view/>
    </div>
</template>

<script>
import MainHeader from "@/components/Layouts/MainHeader";

export default {
    name: 'App',
    components: {MainHeader},
    data: () => ({
        routes: [{
            title: 'Главная',
            to: '/'
        }, {
            title: 'Список задач',
            to: '/todos'
        }]
    })
}
</script>

<style lang="sass">
#app
    font-family: Avenir, Helvetica, Arial, sans-serif
    -webkit-font-smoothing: antialiased
    -moz-osx-font-smoothing: grayscale
    text-align: center
    color: #2c3e50
    margin-top: 60px

*
    margin: 0

button
    cursor: pointer

.app
    display: flex
    flex-direction: column
    align-items: center
    width: 100%

    &__title
        margin-bottom: 20px

    &__hr
        width: 100%
        margin: 32px 0


    &__container
        max-width: 800px
        width: 100%
</style>
