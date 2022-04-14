<script>
    let todos = [
        {done: false, text: 'finish Svelte tutorial'},
        {done: false, text: 'build an app'},
        {done: false, text: 'world domination'}
    ];

    function add(){
        todos = todos.concat({done: false, text: ''});
    }

    function clear(){
        todos = todos.filter(t => !t.done);
    }

    function remove(index){
        const arr = [...todos];
        arr.splice(index, 1)

        todos = arr;
    }

    $: remaining = todos.filter(t => !t.done).length;
</script>

<h1>Todos</h1>

{#each todos as todo,index}
    <div class:done={todo.done}>
        <input
                type=checkbox
                bind:checked={todo.done}
        >

        <input
                placeholder="What needs to be done?"
                bind:value={todo.text}
        >
        <button type="button" on:click={()=>remove(index)}>remove</button>
    </div>
{/each}

<p>{remaining} remaining</p>

<button on:click={add}>
    Add new
</button>

<button on:click={clear}>
    Clear completed
</button>

<style>
    .done {
        opacity:0.4;
    }
</style>