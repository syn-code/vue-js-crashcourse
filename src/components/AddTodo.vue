<template>
    <div>
        <form @submit="addTodo">
            <input type="text" name="title" v-model="title" placeholder="Add Todo..">
            <input type="submit" class="btn" value="Submit"/>
        </form>
    </div>
    
</template>

<script>

import uuid from 'uuid';

export default {
    name: "AddTodo",
    data() {
        return {
            title: '',
        }
    },
    method: {
        addTodo(e) {
            e.preventDetfault();
            //we are not going to add the $emit event to the onsubmit event, we are going to construct the object before we submit it within the event to App.vue
            const newTodo = {
                id: uuid.v4(),
                title: this.title,
                completed: false
            }

            //since the object is constructed we need to send it to the parent App.vue
            //by emitting an event
            //$emit('nameing-convention', parameters to pass)
            this.$emit('add-todo', newTodo);
            this.title = '';
        }
    }
}
</script>

<style scoped>

    form{
        display:flex;
    }

    input[type="text"]{
        flex: 10;
        padding: 5px;
    }

    button[type="subit"] {
        flex: 2;
    }

</style>