<template>
    <header>
        <h1>{{ title }}</h1>
        <Button :text="showAddTask ? 'Close' : 'Add Task'" :color="showAddTask ? 'red' :'green'" @btn-click="$emit('toggle-add-task')"
        />
    </header>
</template>

<script>
import Button from './Button.vue';
export default {
    name: 'Header',
    props: {
        title: {
            title: String,
            default: 'Hello World',
        },
        showAddTask:{
            showAddTask:Boolean
        }
    },
    components: {
        Button
    },
    methods:{
        onClick(){
            this.$emit('toggle-add-task');
        }
    }
}
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}
</style>