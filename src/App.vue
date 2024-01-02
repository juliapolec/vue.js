<template>
    <div>
        <h1>To Do App</h1>
        <ToDoApp/>
    </div>
</template>

<script>
import Todo from './components/ToDoApp.vue'

export default {
    components: {
        ToDoApp: Todo
    }
}
</script>
