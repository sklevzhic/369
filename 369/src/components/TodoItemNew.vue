<template>
    <form v-on:submit.prevent="onSubmit">
        <input type="text" v-model="message">
        <button type="submit">Добавить</button>
    </form>
</template> 

<script>
export default {
    data() {
        return {
            message: ''
        }
    },
    methods: {
        onSubmit: function() {
            if (this.message.trim()) {
                const newTodo = {
                    id: 10,
                    title: this.message,
                    completed: false
                }
                this.$emit('add-todo', newTodo)
            }
        }
    },
}

</script>