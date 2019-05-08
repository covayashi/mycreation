<template>
    <li class="todo-item">{{text}}</li>
</template>

<script>
    export default {
        name: 'TodoItem',
        props: {
            'text': String
        }
    }
</script>