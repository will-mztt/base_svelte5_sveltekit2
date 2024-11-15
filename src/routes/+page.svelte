<script>

    console.log("Hello world");
    let count = $state(0);

    function increment() {
        count += 1;
    }
    // const increment = () => (count += 1);
</script>

<h1>Welcome to SvelteKit</h1>

<button onclick={increment}>
    {count}
</button>
