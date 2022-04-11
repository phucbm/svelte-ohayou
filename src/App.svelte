<script>
    let numbers = [1, 2, 3, 4];

    function addNumber(){
        //numbers.push(numbers.length + 1); // this will not work
        numbers = [...numbers, numbers.length + 1];

        // A simple rule of thumb: the name of the updated variable must appear on the left-hand side of the assignment.
    }

    $: sum = numbers.reduce((t, n) => t + n, 0);
</script>

<p>{numbers.join(' + ')} = {sum}</p>

<button on:click={addNumber}>
    Add a number
</button>