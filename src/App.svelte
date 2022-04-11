<script>
    import Thing from './Thing.svelte';

    let things = [
        {id: 1, name: 'apple'},
        {id: 2, name: 'banana'},
        {id: 3, name: 'carrot'},
        {id: 4, name: 'doughnut'},
        {id: 5, name: 'egg'},
    ];

    function handleClick(){
        things = things.slice(1);
    }

    // Here, (thing.id) is the key, which tells Svelte how to figure out which DOM node to change when the component updates.

    // You can use any object as the key, as Svelte uses a Map internally — in other words you could do (thing) instead of (thing.id).
    // Using a string or number is generally safer, however, since it means identity persists without referential equality,
    // for example when updating with fresh data from an API server.
</script>

<button on:click={handleClick}>
    Remove first thing
</button>

{#each things as thing (thing.id)}
    <Thing name={thing.name}/>
{/each}
