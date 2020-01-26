<template>
    <div>
        <div v-bind:key="todo.id" v-for="todo in todos">
            <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"/>
        </div>
    </div>
</template>

<script>

import TodoItem from '../components/TodoItem'

export default {
    //compnent name: goes here
    name: "Todos",
    components:{
        TodoItem
    },
    /*
        Accepting the props that are being passed into the component in                      App.vue. These will be passed in with v-bind
    */
    props: ["todos"]
}
</script>

<style lang="stylus" scoped>

</style>