<template>
    <li v-bind:class="{ done: todo.completed }"> 
        <input type="checkbox" v-on:change = " todo.completed = !todo.completed ">
        {{ todo.title }}
        <button v-on:click="$emit('remove-todo', todo.id)">X</button>
    </li>
</template> 

<script>
export default {
    props: {
        todo: {
            type: Object,
            required: true
        }
    }
}

</script>