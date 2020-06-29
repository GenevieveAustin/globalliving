<script>
    import { stores } from '@sapper/app'
    const { session } = stores()

    import { goto } from '@sapper/app';

    function saveAndGo() {
        session.user = name
        goto('gen')
    }

    let name = ''
</script>

<style>
</style>

<h1 class="title">Log in</h1>

<label>Please enter your name: <input type="text" bind:value={name}> </label>

<button on:click={saveAndGo}>Next</button>

