<script lang="ts">
    import TaskDescription from "./TaskDescription.svelte";
    import type { ITask } from "../types/types";

    export let taskData: ITask = { id: 0, description: '' };

    let taskDescriptionHidden:boolean = true;

    $: () => {
        console.log(taskData);
    }

    const openTaskDialog = () => {
        taskDescriptionHidden = false;
    }

    const closeTaskDialog = () => {
        console.log('entro');
        taskDescriptionHidden = true;
    }

</script>

<style>
    .task-main-container {
        border-radius: 15px;
        display: flex;
        flex-direction: row;
        font-size: 12;
        padding: 0 1rem 0 1rem;
        box-shadow: rgba(0, 0, 0, 0.15) 0px 5px 15px 0px
    }

    .text-container {
        flex-basis: 80%;
        max-width: fit-content;
        padding: 0 1rem 0 1rem;
        display: flex;
        flex-wrap: nowrap;
    }

    .inline-text {
        display: inline;
    }

    .flex-start {
        align-self: flex-start;
    }

    .column-1 {
        flex-basis: 20%;
        margin-right: 1rem;
    }

    .text-overflow {
        text-overflow: ellipsis;
        white-space: nowrap;
        overflow: hidden;
    }

    .column-2 {
        flex-basis: 80%;
    }
</style>

<TaskDescription hidden={taskDescriptionHidden} on:childEvent={closeTaskDialog}/>

<div class="task-main-container">
    <input type="checkbox"/>
    <button style="all: unset" on:click={openTaskDialog}>
        <span class="text-container text-overflow">
            <p class="column-1 inline-text flex-start">{taskData.id}</p>
            <p class="column-2 inline-text">{taskData.description}</p>
        </span>
    </button>
</div>

