<script>
    import Inner from './Inner.svelte';
    import Outer from "./Outer.svelte";

    function handleMessage(event){
        console.log(event)
    }
</script>

<Outer on:myevent={handleMessage}/>