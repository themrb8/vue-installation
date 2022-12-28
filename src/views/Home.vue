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
        <div class="flex flex-wrap -mx-4">
            <div v-for="todo in todos" class="w-1/3 px-4 mt-6">
                <h3 class=" bg-slate-300 font-semibold p-2 rounded-sm h-full">{{ todo.title }}</h3>
            </div>
        </div>
    </div>
</template>