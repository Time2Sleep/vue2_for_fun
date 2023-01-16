<template>
    <header class="main-header">
        <div class="main-header__space"></div>
        <nav class="nav">
            <template v-for="route in routes">
                <router-link class="nav__link"
                             :class="{active: $route.path === route.to}"
                             :to="route.to"
                >
                    {{ route.title }}
                </router-link>
            </template>
            {{ }}
        </nav>
    </header>

</template>

<script>
export default {
    name: "MainHeader",
    props: {
        routes: Array
    }
}
</script>

<style scoped lang="sass">
.main-header
    &__space
        height: 7rem
.nav
    position: fixed
    top: 0
    left: 0
    width: 100%
    padding: 3rem
    background: white
    box-shadow: 0 4px 20px rgb(0 0 0 / 10%)
    display: flex
    justify-content: flex-start
    &__link
        text-decoration: none
        font-size: 20px
        color: #333
        &.active
            text-decoration: underline
        & + .nav__link
            margin-left: 4rem
</style>