<script>
export default {
    name: 'Home',
    data() {
        return {
            todos: []
        }
    },
    mounted() {
        fetch('https://jsonplaceholder.typicode.com/todos/')
        .then(response => response.json())
        .then(json => this.todos = json)
    }
}
</script>

<template>
    <div class="container mx-auto">
        <div v-for="todo in todos" class="flex-wrap justify-between items-center bg-slate-300 p-2 rounded-sm mb-4">
            <div class="item">
                <h3 class="font-semibold ">{{ todo.title }}</h3>
            </div>
        </div>
    </div>
</template>