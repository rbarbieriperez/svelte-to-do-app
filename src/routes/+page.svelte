<script lang="ts">
    import Task from "../components/Task.svelte";

    const taskData = {
        description: 'Ir a hacer las compras',
        id: 1,
    }
</script>

<main>
    <Task taskData={taskData}/>
</main>

