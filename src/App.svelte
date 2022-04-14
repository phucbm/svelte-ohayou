<script>
    async function getRandomNumber(){
        const res = await fetch(`https://my-json-server.typicode.com/phucbm/svelte-ohayou/svelte-db`);
        const text = await res.text();

        if(res.ok){
            return JSON.parse(text);
        }else{
            throw new Error(text);
        }
    }

    let promise = getRandomNumber();

    function handleClick(){
        promise = getRandomNumber();
    }
</script>

<button on:click={handleClick}>
    generate random number
</button>

{#await promise then value}
    <p>the value is {value.number}</p>
{/await}