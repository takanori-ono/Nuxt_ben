<template>
    <div style="margin: 50px;">
        <ul>
            <li v-for="todo in todos">
                <input type="checkbox" :checked="todo.done" @change="toggle(todo)">
                <span :class="{ done: todo.done }">{{ todo.text }}</span>
            </li>
        </ul>
        <input placeholder="タスクを追加してください" @keyup.enter="addTODO">
    </div>
</template>

<script>
import { mapMutations } from 'vuex'

export default {
    computed: {
        todos () {
            return this.$store.state.todos.list
        }
    },
    methods: {
        addTODO(e){
            this.$store.commit('todos/add', e.target.value)
        },
        ...mapMutations({
            toggle: 'todos/toggle'
        })
    }
}
</script>

<style>
.done{
    text-decoration: line-through;
}
</style>