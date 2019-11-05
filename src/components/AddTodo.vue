<template>
    <div>
        <form @submit.prevent="addTodo">
            <input type="text" v-model="title" name="title" placeholder="let's do something fun ☺">
            <input type="submit" value="Click to add" class="btn">
        </form>
    </div>
</template>

<script>

export default {
    name: "AddTodo",
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addTodo() {
                const newTodo = {
                title: this.title,
                completed: false
            }
            // send up to parent
            this.$emit('add-todo', newTodo);
        }
    }
}
</script>

<style scoped>
    form {
        display: flex;
    }
    input[type="text"] {
        flex: 5;
        padding: 15px;
        font-size: 20px;
    }

    input[type="submit"] {
        flex: 3;
        font-size: 20px;
    }

    
</style>