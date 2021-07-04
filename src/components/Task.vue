<template>
    <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder':'','task']">
        <h3>{{ task.text }}
            <i @click="onDelete(task.id)" class="fas fa-times"></i>
        </h3>
        <p>{{ task.day }}</p>
    </div>
</template>
<script>
export default{
    name : 'Task',
    props:{
        task: Object
    },
    methods:{
        onDelete(id){
            this.$emit("delete-task",id)
        }
    }
}
</script>
<style>
    .task{
        background:rgb(228, 223, 223)
    }
    .reminder{
        border-left: 5px solid green;
    }
    .fas{
        color:red
    }
</style>