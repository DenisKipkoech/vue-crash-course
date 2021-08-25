<template>
    <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder' : '', 'task']">
        <h3>{{ task.text }}
            <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
        </h3>
        <p>{{ task.day }}</p>
    </div>
</template>

<script>
export default {
    name:'Task',
    props:{
        task: Object
    }
}
</script>

<style scoped>
    .fas {
        color: tomato;
    }

    .task {
        background: #f4f4f4;
        padding: 0.3em 1em;
        margin: 0.2em;
        cursor: pointer;
    }

    .task h3 {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .task.reminder{
        border-left: 5px solid green;
    }
</style>