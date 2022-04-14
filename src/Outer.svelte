<script>
    import Inner from './Inner.svelte';
    import {createEventDispatcher} from 'svelte';

    const dispatch = createEventDispatcher();

    function forward(e){
        dispatch('myevent', e)
    }
</script>

<Inner on:myevent={forward}/>