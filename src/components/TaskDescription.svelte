<style>

    .dialog-veil {
        position: absolute;
        width: 100%;
        height: 100%;
        background-color: lightgray;
        opacity: 0.7;
    }
    
    .task-description-main-container {
        width: 90%;
        height: 80%;
        background-color: white;
        z-index: 999;
        border-radius: 25px;
    }

    .center {
        position: absolute;
        left: 0;
        right: 0;
        top: 0;
        bottom: 0;
        margin: auto;
    }

    .title {
        text-align: center;
    }

    .close-button {
        width: .8rem;
        height: .8rem;
        position: absolute;
        top: 1.2rem;
        right: 1.2rem;
    }


</style>

<script lang="ts">
    import close from '../images/close.png';

    export let hidden:boolean = true;

    const toggleVisibility = () => {
        dispatchEvent(new CustomEvent('task-description-event', { bubbles: true, composed: true, detail: true }));
    }

</script>

<div class="task-description-main-container center" hidden={hidden}>
    <p class="title">Task Information</p>
    <button on:click={toggleVisibility} style="all: unset">
        <img class="close-button" src={close} alt="close button">
    </button>
</div>

<div class="dialog-veil" hidden={hidden}></div>
