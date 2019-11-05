<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete" v-bind:checked="todo.completed"> 
            {{todo.title}}
            <button @click="$emit('del-todo', todo.id)" class="del">remove</button>
            </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
    .todo-item {
        background: #f4f4f4;
        padding: 5px;
        border-bottom: 1px #cccccc solid;
        font-size: 20px;
    }

    .is-complete {
        text-decoration: line-through;
        text-emphasis-color: gray;
     
    }

    .del {
        background: #ff0000;
        color: #fff;
        border: none;
        padding: 7px 15px;
        border-radius: 10%;
        cursor: pointer;
        float: right;
        text-align: center;
        font-size: 16px;
    }
</style>