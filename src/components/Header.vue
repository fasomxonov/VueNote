<template>
    <header>
        <h1>{{ title }}</h1>
        <Button @toggle-add-task="$emit('toggle-add-task')" :text="showAddTask ? 'close': 'add'" color="green" />
    </header>
</template>

<script>
import Button from '@/components/Button'
export default {
    name: 'Header',
    components: {
        Button,
    },
    props: {
        title: String,
        showAddTask: Boolean,
    },
    emits: [
        'toggle-add-task',
    ]
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