<script>
    import Inner from './Inner.svelte';

    function handleMessage(event){
        console.log(event)
    }
</script>

<Inner on:myevent={handleMessage}/>