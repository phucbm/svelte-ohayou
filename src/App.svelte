<script>
    import Info from './Info.svelte';

    const pkg = {
        name: 'svelte',
        version: 3,
        speed: 'blazing',
        website: 'https://svelte.dev',
        undeclaredValue: 'Undeclared value!',
    };
</script>

<Info {...pkg}/>